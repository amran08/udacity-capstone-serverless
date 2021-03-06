[![Build Status](https://travis-ci.org/amran08/udacity-capstone-serverless.svg?branch=master)](https://travis-ci.org/amran08/udacity-capstone-serverless)

# Github Repo Link
https://github.com/amran08/udacity-capstone-serverless

# Serverless TODO

This repository implements a simple TODO application using AWS Lambda and Serverless framework.

There are two components of the Project
 - Backend 
 - Client 

# Functionality of the application

This application will allow CRUD actions.Each TODO item can optionally have an attachment image. Each user only has access to TODO items associated to the creator.

# Backend
The `backend` folder contains the AWS lamda functions which provide the Serverless Todo API. 

It is built and deployed to AWS using TravisCI on each push to master/dev/prepod branches

`.travis.yml` is located at the root of the project

## Endpoints:
  * GET - https://{{apiid}}.execute-api.ap-southeast-1.amazonaws.com/prod/todos
  * POST - https://{{apiid}}.execute-api.ap-southeast-1.amazonaws.com/prod/todos
  * PATCH - https://{{apiid}}.execute-api.ap-southeast-1.amazonaws.com/prod/todos/{todoId}
  * DELETE - https://{{apiid}}.execute-api.ap-southeast-1.amazonaws.com/prod/todos/{todoId}
  * POST - https://{{apiid}}.execute-api.ap-southeast-1.amazonaws.com/prod/todos/{todoId}/attachment

# Frontend

The `client` folder contains a web application that can uses the API for Serverless Todo.

The `Jenkinsfile` is located at the project root. 
This can be configured to be built and deployed on each commit/ pull request using github hooks.

## Authentication

We used auth0 for authentication

# How to run the application

## Backend

To deploy an application run the following commands:

```
cd backend
npm install
sls deploy -v
```

## Frontend

To run a client application first edit the `client/src/config.ts` file to set correct parameters. And then run the following commands:

```
cd client
npm install
npm run start
```

This should start a development server with the React application that will interact with the serverless TODO application.


## CI/CD 

Added jenkins file which contains stages of deploying frontend app in S3

# Postman collection

An alternative way to test your API, you can use the Postman collection that contains sample requests. You can find a Postman collection in this project. To import this collection, do the following.

Click on the import button:

![Alt text](images/import-collection-1.png?raw=true "Image 1")


Click on the "Choose Files":

![Alt text](images/import-collection-2.png?raw=true "Image 2")


Select a file to import:

![Alt text](images/import-collection-3.png?raw=true "Image 3")


Right click on the imported collection to set variables for the collection:

![Alt text](images/import-collection-4.png?raw=true "Image 4")

Provide variables for the collection (similarly to how this was done in the course):

![Alt text](images/import-collection-5.png?raw=true "Image 5")
