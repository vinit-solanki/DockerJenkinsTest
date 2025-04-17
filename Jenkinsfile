pipeline {
agent any
stages {
stage('Checkout Code') {
steps {
git branch: 'main', url: 'https://github.com/vinit-solanki/Jenkins-Test'
}
}
stage('Build Docker Image') {
steps {
dir('DockerJenkinsExperiment') { // Ensure Docker build happens in the
right folder
sh 'ls -l' // Debugging: List files to check if Dockerfile exists
sh 'docker build -t my-docker-webapp .' // Build Docker Image
}
}

}
stage('Run Docker Container') {
steps {
sh 'docker run -d -p 8081:80 my-docker-webapp'
}
}
}
}
    agent any
    
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    echo 'Building Docker Image...'
                    // Use bat instead of sh on Windows
                    bat 'docker build -t my-docker-webapp .'
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    echo 'Running Docker Container...'
                    // Use bat instead of sh on Windows
                    bat 'docker run -d -p 8081:80 my-docker-webapp'
                }
            }
        }
    }
}
