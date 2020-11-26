pipeline {
    agent {
        label 'master'
    }
    environment{
        PATH=sh(script:"echo $PATH:/usr/local/bin", returnStdout:true).trim()
        AWS_REGION = "us-east-1"
        AWS_ACCOUNT_ID=sh(script:'export PATH="$PATH:/usr/local/bin" && aws sts get-caller-identity --query Account --output text', returnStdout:true).trim()
        ECR_REGISTRY="${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_REGION}.amazonaws.com"
        APP_REPO_NAME = "clarusway-repo/phonebook-app"
        APP_NAME = "phonebook"
        AWS_STACK_NAME = "Serdar-Phonebook-App-${BUILD_NUMBER}"
    }
    stages {
        stage('creating ECR Repository') {
            steps {
                echo 'creating ECR Repository'
                sh 'echo ${GIT_URL}'
            }
        }
        stage('building Docker Image') {
            steps {
                echo 'building Docker Image'
            }
        }
        stage('pushing Docker image to ECR Repository'){
            steps {
                echo 'pushing Docker image to ECR Repository'
            }
        }
        stage('creating infrastructure for the Application') {
            steps {
                echo 'creating infrastructure for the Application'
            }
        }
        stage('Deploying the Application'){
            steps {
                echo 'Deploying the Application'
            }
        }
    }
    post {
        always {
            echo 'Goodbye ALL... Please come back soon'
        }
        failure {
            echo 'Sorry but you messed up...'
        }
        success {
            echo 'You are the man/woman...'
        }
    }