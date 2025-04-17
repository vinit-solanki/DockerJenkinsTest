pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/vinit-solanki/DockerJenkinsTest.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-docker-webapp .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 8081:80 --name webapp-container my-docker-webapp'
            }
        }
    }
}