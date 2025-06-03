

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
- Messaging Service layer
    - 
