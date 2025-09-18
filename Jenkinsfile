pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 sanjana3082004/registration:v1'
                bat 'docker push sanjana3082004/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f D:/22251A1280/deployment.yaml'
                bat 'kubectl apply -f D:/22251A1280/service.yaml'
            }
        }
        
    }
}
