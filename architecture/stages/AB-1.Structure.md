
---
## Backend Architecture (Control plane)
### Users Module
- Users can signup and signin using Clerk and OAuth.
- Users can connect to their GitHub account using OAuth scope `public repo` and `email` access.
- Users can view their connected GitHub account and its status.
- Users can get their profile information.
- Users can update their profile information.
- Users can delete their account. (not implemented yet)


### Deployment Module
- Users can select a repository, branch, and Dockerfile path from their connected GitHub account.
- Users can upload environment variables. (not implemented yet)
- Users can update their deployment configuration.
- Users can select the endpoints for the backend hosted.
- Users can update the endpoints for the backend hosted.
- Users can delete the endpoints for the backend hosted.


### Messaging-Queue Module
- Deployment trigger for creating and publishing messages to the queue.
- Messaging Service layer
    - Create the exchange and queue in RabbitMQ.
    - Create a publishdeploymentdto to publish the deployment message.
    - OnModuleInit to create the exchange and queue.
    - OnModuleDestroy to delete the exchange and queue.
    - Publish method to publish the deployment message.
- Create a persistent volume for rabbitmq and docker compose setup.


---

## MQ Architecture (Rabbitmq)
- Implemented direct queue
- exchangeName : "blacktree.direct"

| Direction        | Exchange           | Routing Key      | Queue           | Producer | Consumer |
| ---------------- | ------------------ | ---------------- | --------------- | -------- | -------- |
| backend → worker | `blacktree.direct` | `worker.execute` | `execute.queue` | API      | Worker   |
| worker → backend | `blacktree.direct` | `api.result`     | `status.queue`  | Worker   | API      |


![alt text](image.png)

---
## Worker (Go)
## Worker Architecture
### Queue Handling (queue)
- Consume messages from the RabbitMQ queue.
- Acknowledge message only after full process (clone → build → status).
-  Separate routing keys for:
        api.clone.register
        api.deploy.request
- Publish status updates back to the backend 


### repository (repo)
- Clone the repository from GitHub.
- Authenticate if token is provided (private repos).
- Create timestamped folder: `tmp/repos/<repo-name>-<timestamp>`
- Clone repo into that directory.
- Track clone info in tracker file (repos.json):
    status: cloned
- If failed: skip build and send failed status.


### builder (builder)
- Build the Docker image using the Dockerfile.
- Use the timestamped folder from the clone step.
- Build the image with a unique tag: `blacktree/<repo-name>:<timestamp>
- if build completes remove folder whose entry is in `repos.json` and for successful build update the status in the sqlite db to `built` and compose file after sanitasition
- if docker compose file exists, run the docker compose file and send the status as running to backend.


### runner (runner)
- run the docker containers using the built image.
- use assigned port from `port pool`.
- If the container is running, send the status as running to backend.
- If the container fails to run, send the status as failed to backend. 
- If the docker compose file fails to run, send the status as failed to backend and.

### tracker (tracker)
- SaveEntry(): Log clone info (repo, path, status).
- MarkAsBuilt(): Update status once image is built.
- DeleteEntry(): Delete folder if status is built or failed after N mins.



| Package    | Responsibility                    |
| ---------- | --------------------------------- |
| `queue/`   | MQ consumer/publisher             |
| `repo/`    | Cloning logic                     |
| `builder/` | Docker image build                |
| `runner/`  | Run container or compose          |
| `tracker/` | File-based tracker for cleanup    |
| `ports/`   | Port pool logic                   |
| `store/`   | SQLite DB for persistent mappings |
| `utils/`   | Time, string helpers, logger      |
