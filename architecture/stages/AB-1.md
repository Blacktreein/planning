# AB-1 (API Builder 1) - June 2025

This version is AB-1 (API builder 1). Features include

> [!NOTE]
> For description of tasks, please refer to the [Structure](./AB-1.Structure.md) document.

| Task                                               | Status  | Names |
| -------------------------------------------------- | ------- | ----- |
| Signup and Signin                                  | ✅ Done | auth  |
| Connect to github                                  | ✅ Done | repo1 |
| Select repository, branch and dockerfile path      | ✅ Done | repo2 |
| Select environment variables                       | ❌      | conf1 |
| Select build and deploy options                    | ❌      | conf2 |
| Create message and connect backend to queue                | ✅ Done   | msg1  |
| Implement messaging queue                          | ✅ Done      | msg2  |
| Create go worker with docker sdk to deploy locally | ❌      | wrk1  |

## Signup and Signin

- Users can signup and signin using clerk and oauth

## Connect to github

- Users can connect to their github account using oauth scope `public repo` and `email` access

| Task                                                                                                          | Status  | Tags       |
| ------------------------------------------------------------------------------------------------------------- | ------- | ---------- |
| Create github oauth app and its entire setup                                                                  | ✅ Done | 🎨Frontend |
| Create an sso page for redirect with github oauth code                                                        | ✅ Done | 🎨Frontend |
| Create a backend endpoint to handle the exchange of the code for an access token and update the accesss token | ✅ Done | 🐍Backend  |
| Create a context to manage the state if user has connected to github                                          | ✅ Done | 🎨Frontend |
| Create a me route for the user to see their connected github account                                          | ✅ Done | 🐍Backend  |
| Update sync db route to give info about the user along with github status                                     | ✅ Done | 🐍Backend  |

## Select repository, branch and dockerfile path

- Users can select a repository, branch and dockerfile path from their connected github account

| Task                                                                                    | Status  | Tags       |
| --------------------------------------------------------------------------------------- | ------- | ---------- |
| Create a route to get the list of repositories for the user                             | ✅ Done | 🐍Backend  |
| Create a route to get the list of branches for the selected repository                  | ✅ Done | 🐍Backend  |
| Create Frontend component to select repository, branch and dockerfile path              | ✅ Done | 🎨Frontend |
| Create a deployment entity to store the selected repository, branch and dockerfile path | ✅ Done | 🐍Backend  |
| Service layer for deployment module and store the data in the database                  | ✅ Done | 🐍Backend  |
| Controller layer for deployment module to handle the request and response               | ✅ Done | 🐍Backend  |
| entity for endpoints which will be of the backend hosted                                | ✅ Done | 🐍Backend  |
| service layer for endpoints to handle the logic                                         | ✅ Done | 🐍Backend  |
| controller for the endpoints to handle endpoints                                        | ✅ Done | 🐍Backend  |

## Create message and connect backend to queue

- A messaging queue is created and is connected to the main backend for deployemnt
- 

| Task                                                                                | Status  | Tags          |
| ----------------------------------------------------------------------------------- | ------- | ------------- |
| Create a route to trigger a message for the deployment                              | ✅ Done | 🐍Backend     |
| RabbitMQ setup and configuration from docker compose                                | ✅ Done | 🐍Backend     |
| A queue named 'deployments' is created in RabbitMQ                                  | ✅ Done | Message Queue |
| Create a messaging queue module (Tasks)[./AB-1.Structure.md#messaging-queue-module] | ✅ Done | 🐍Backend     |
| Create a message DTO                                                                | ✅ Done | 🐍Backend     |
| Setup rabbitmq publisher logic                                                      | ✅ Done | 🐍Backend     |
| Test/health check endpoints for the messaging queue module                          | ✅ Done      | 🐍Backend     |
| Integrate messaging queue into deployment module (trigger endpoint)                 | ✅ Done | 🐍Backend     |

## Implement messaging queue (msg2)
- 

## Select environment variables (Later)
- Users can upload the environment variables

## Select build and deploy options (Later)
- Users can select the build and deploy options like build command, deploy command, etc.


## Create go worker with docker sdk to deploy locally (wrk1)
- A worker is created to handle the deployment requests and manage the Docker engine [[AB-1.Structure.md#worker-go]].


# AB-1 (API Builder 1) - June 2025

This version is AB-1 (API builder 1). Features include

> \[!NOTE]
> For description of tasks, please refer to the [Structure](./AB-1.Structure.md) document.

| Task                                               | Status | Names |
| -------------------------------------------------- | ------ | ----- |
| Signup and Signin                                  | ✅ Done | auth  |
| Connect to github                                  | ✅ Done | repo1 |
| Select repository, branch and dockerfile path      | ✅ Done | repo2 |
| Select environment variables                       | ❌      | conf1 |
| Select build and deploy options                    | ❌      | conf2 |
| Create message and connect backend to queue        | ✅ Done | msg1  |
| Implement messaging queue                          | ❌      | msg2  |
| Create go worker with docker sdk to deploy locally | ❌      | wrk1  |

## Signup and Signin

* Users can signup and signin using clerk and oauth

## Connect to github

* Users can connect to their github account using oauth scope `public repo` and `email` access

| Task                                                                                                          | Status | Tags       |
| ------------------------------------------------------------------------------------------------------------- | ------ | ---------- |
| Create github oauth app and its entire setup                                                                  | ✅ Done | 🎨Frontend |
| Create an sso page for redirect with github oauth code                                                        | ✅ Done | 🎨Frontend |
| Create a backend endpoint to handle the exchange of the code for an access token and update the accesss token | ✅ Done | 🐍Backend  |
| Create a context to manage the state if user has connected to github                                          | ✅ Done | 🎨Frontend |
| Create a me route for the user to see their connected github account                                          | ✅ Done | 🐍Backend  |
| Update sync db route to give info about the user along with github status                                     | ✅ Done | 🐍Backend  |

## Select repository, branch and dockerfile path

* Users can select a repository, branch and dockerfile path from their connected github account

| Task                                                                                    | Status | Tags       |
| --------------------------------------------------------------------------------------- | ------ | ---------- |
| Create a route to get the list of repositories for the user                             | ✅ Done | 🐍Backend  |
| Create a route to get the list of branches for the selected repository                  | ✅ Done | 🐍Backend  |
| Create Frontend component to select repository, branch and dockerfile path              | ✅ Done | 🎨Frontend |
| Create a deployment entity to store the selected repository, branch and dockerfile path | ✅ Done | 🐍Backend  |
| Service layer for deployment module and store the data in the database                  | ✅ Done | 🐍Backend  |
| Controller layer for deployment module to handle the request and response               | ✅ Done | 🐍Backend  |
| entity for endpoints which will be of the backend hosted                                | ✅ Done | 🐍Backend  |
| service layer for endpoints to handle the logic                                         | ✅ Done | 🐍Backend  |
| controller for the endpoints to handle endpoints                                        | ✅ Done | 🐍Backend  |

## Create message and connect backend to queue

* A messaging queue is created and is connected to the main backend for deployment

| Task                                                                                 | Status | Tags          |
| ------------------------------------------------------------------------------------ | ------ | ------------- |
| Create a route to trigger a message for the deployment                               | ✅ Done | 🐍Backend     |
| RabbitMQ setup and configuration from docker compose                                 | ✅ Done | 🐍Backend     |
| A queue named 'deployments' is created in RabbitMQ                                   | ✅ Done | Message Queue |
| Create a messaging queue module (Tasks)\[./AB-1.Structure.md#messaging-queue-module] | ✅ Done | 🐍Backend     |
| Create a message DTO                                                                 | ✅ Done | 🐍Backend     |
| Setup rabbitmq publisher logic                                                       | ✅ Done | 🐍Backend     |
| Test/health check endpoints for the messaging queue module                           | ✅ Done | 🐍Backend     |
| Integrate messaging queue into deployment module (trigger endpoint)                  | ✅ Done | 🐍Backend     |

## Implement messaging queue (msg2)

* Add consumer logic to receive deployment messages
* Retry mechanism or error logging for failed message processing

## Select environment variables (Later)

* Users can upload the environment variables

## Select build and deploy options (Later)

* Users can select the build and deploy options like build command, deploy command, etc.

## Create go worker with docker sdk to deploy locally (wrk1)

* A worker is created to handle the deployment requests and manage the Docker engine \[\[AB-1.Structure.md#worker-go]].

| Task                                                                                          | Status | Tags   |
| --------------------------------------------------------------------------------------------- | ------ | ------ |
| Consume messages from RabbitMQ queue for deployment requests                                   | ✅ Done     | worker |
| Clone the GitHub repository based on the deployment request                                   | ✅ Done      | worker |
| Track cloned repository with timestamp and metadata                                           | ✅ Done      | worker |
| Build Docker image from the specified Dockerfile path                                         | ❌      | worker |
| Store build status (success/failure) and update tracker accordingly                           | ❌      | worker |
| Handle optional Docker Compose file usage                            | ❌      | worker |
| Run the container and expose selected or available port safely                                | ❌      | worker |
| Maintain a dynamic pool of ports and allocate a free one for new deployments                  | ❌      | worker |
| Periodically clean up old/failure builds and remove containers/images and update tracker file | ❌      | worker |
| Store image/container/port metadata in SQLite (optional improvement)                          | ❌      | worker |
| Publish status updates to messaging queue with appropriate routing key                        | ❌      | worker |
