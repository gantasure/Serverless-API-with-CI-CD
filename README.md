# Serverless API with CI/CD

This project demonstrates how to create a serverless API using AWS Lambda and the Serverless Framework, and how to set up a CI/CD pipeline with Jenkins and Docker.

## Project Structure
serverless-api-cicd/
├── handler.js        # Lambda function code
├── serverless.yml    # Serverless Framework configuration
├── Dockerfile        # Dockerfile for build environment
├── .dockerignore
├── Jenkinsfile
└── README.md


## Technologies Used

*   Node.js
*   AWS Lambda
*   Serverless Framework
*   Docker
*   Jenkins
*   Git/GitHub

## Setup

1.  **AWS Setup:**
    *   Create an AWS account.
    *   Configure your AWS credentials (access key ID and secret access key).

2.  **Serverless Framework:**
    *   Install the Serverless Framework globally: `npm install -g serverless`

3.  **Jenkins:**
    *   Install Jenkins.
    *   Install the Git plugin.
    *   Add your AWS credentials as a "Secret text" credential in Jenkins (ID: `aws-creds`).

4.  **GitHub Webhook:**
    *   Configure a GitHub webhook to trigger the Jenkins pipeline on push events.

## Deployment

1.  Commit and push your changes to your GitHub repository.
2.  The Jenkins pipeline will automatically:
    *   Checkout the code.
    *   Build and push the docker image.
    *   Use the Serverless Framework to deploy the Lambda function to AWS.

## Testing

After deployment, you'll get an endpoint URL in the Jenkins console output (or you can find it in the AWS Lambda console). Access this URL to test your Lambda function.

## Cleanup

To remove the deployed Lambda function, run `sls remove` in the project directory.
