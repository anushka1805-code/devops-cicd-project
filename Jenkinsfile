pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/anushka1805-code/devops-cicd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app:latest .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f devops-app-container || true'
                sh 'docker run -d --name devops-app-container -p 4000:3000 devops-app:latest'
            }
        }
    }
}