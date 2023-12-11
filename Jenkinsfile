pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/praateek99/sam-app.git'
            }
        }

        stage('Build') {
            steps {
                sh 'sam build'
            }
        }

        stage('Deploy') {
            steps {
                withAWS(credentials: 'aws-sam-key') {
                    sh 'sam deploy --stack-name sam-app --capabilities CAPABILITY_IAM'
                }
            }
        }
    }
}
