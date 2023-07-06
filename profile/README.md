# Task Management Project

Welcome to the Task Management project. This README will guide you on how to set up Postman, import our Postman collection, and get started with running our API and UI locally. We also provide information on how to use our Jira Kanban board and Slack Channel.

## Jira Kanban Board

Our team uses a Jira Kanban Board to manage and track the progress of our work. 

[Jira Board](https://cmsc495group1.atlassian.net/jira/software/projects/CMSC495/boards/1)

## Slack Channel

We use Slack for our team communication. 

[Slack Group](https://app.slack.com/client/T05DE2PNXNV/C05CLT6MULF)

## Setting Up Postman

1. Download and install Postman from [Postman's official site](https://www.postman.com/downloads/).
2. Launch Postman and sign in or sign up.

### Importing Postman Collection

1. In Postman, click on the "Import" button.
2. Click on "Link".
3. Paste the following link into the textbox: 
   [Postman Collection](https://github.com/CMSC-495-Group-One/TaskManagementAPI/blob/main/Postman%20Collections/postman-collection.json)
4. Click on "Continue" and then "Import" to confirm.

### Running Our Collection

1. After importing, you can see our collection in the "Collections" sidebar.
2. Click on the collection name to expand it and see the different API requests.

### Authentication

**Note:** By including the `Authorization` header with the `Bearer <authentication_token>` value, you simulate an authenticated request in Postman. The backend will then validate the token and allow access to the authenticated endpoint.

### Obtaining an authentication token:

1. Send a `POST` request to the backend `/v1/auth/signin` endpoint with valid credentials.
2. A script stores the `accessToken` as an environment variable in Postman and is used in all other HTTP calls.

This is for your convenience. You won’t need to copy and paste it anywhere.

### Testing the authenticated endpoints:

1. Make the request to the authenticated endpoint (eg. `/v1/users`, `/v1/tasks`) in Postman.
2. The backend will validate the authentication token included in the `Authorization` header and process the request accordingly. The response will contain the JSON body if the token was valid. 

- If you receive a status `401`, the API is properly working. You just need a new token. See **Obtaining an authentication token** section.
- If you receive a status `500`, there was an internal server error. Attempt to create a new user using the `/v1/auth/signup` endpoint. If you receive a status `2xx`, you can sign in using step 1 in **Obtaining an authentication token** section. Otherwise, there is a bug.

---

Feel free to contribute to this project and help us improve. Thank you for using our Task Management API!
