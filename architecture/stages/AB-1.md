# AB-1 (API Builder 1) - June 2025

This version is AB-1 (API builder 1). Features include

| Task                                               | Status  | Names |
| -------------------------------------------------- | ------- | ----- |
| Signup and Signin                                  | ✅ Done | auth  |
| Connect to github                                  | ✅ Done | repo1 |
| Select repository, branch and dockerfile path      | ❌      | repo2 |
| Select environment variables                       | ❌      | conf1 |
| Select build and deploy options                    | ❌      | conf2 |
| Create message and connect to queue                | ❌      | msg1  |
| Implement messaging queue                          | ❌      | msg2  |
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

| Task                                                                                    | Status     | Tags       |
| --------------------------------------------------------------------------------------- | ---------- | ---------- |
| Create a route to get the list of repositories for the user                             | ✅ Done    | 🐍Backend  |
| Create a route to get the list of branches for the selected repository                  | ✅ Done    | 🐍Backend  |
| Create Frontend component to select repository, branch and dockerfile path              | ✅ Done    | 🎨Frontend |
| Create a deployment entity to store the selected repository, branch and dockerfile path | `📌 Major` | 🐍Backend  |
| Service layer for deployment module and store the data in the database                  | `📌 Major` | 🐍Backend  |

## Select environment variables (Later)

- Users can upload the environment variables

## Select build and deploy options (Later)

- Users can select the build and deploy options like build command, deploy command, etc.

## Create message and connect to queue

- A messsage is created and connected to the queue for the deployment
  | Task | Status | Tags |
  | ------------------------------------------------- | ------- | ----- |
  | Create a route to create a message for the deployment | `📌 Major` | 🐍Backend |
  |
