
pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/LAVANYA-ASUTI/devops-projects.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t lavanya/devops-app .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                bat 'docker push lavanya/devops-app'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml'
            }
        }
    }
}