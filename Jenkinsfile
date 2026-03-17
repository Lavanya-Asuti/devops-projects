
pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/LAVANYA-ASUTI/devops-projects.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t lavanyaasuti/devops-app .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                sh 'docker push lavanyaasuti/devops-app'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}