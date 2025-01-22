pipeline {
    agent {
        docker {
            image 'node:18-alpine' // Use the Node image for basic tasks
        }
    }
    triggers {
        githubPush()
    }
    stages {
        stage('Build and Deploy') {
            steps {
                git branch: 'test', url: 'https/gantasure6786@/serveless-api-with-CI-CD/l' # Replace with your repo URL
                withCredentials([usernamePassword(credentialsId: 'aws-creds', usernameVariable: 'AWS_ACCESS_KEY_ID', passwordVariable: 'AWS_SECRET_ACCESS_KEY')]) {
                    sh '''
                        apk add --no-cache python3 py3-pip make g++
                        pip3 install awscli
                        npm install -g serverless
                        sls deploy --verbose
                    '''
                }
            }
        }
    }
}
