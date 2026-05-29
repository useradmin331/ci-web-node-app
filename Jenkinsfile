pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                url: 'https://github.com/useradmin331/ci-web-node-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t web-devops-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker rm -f web-container'
                bat 'docker run -d -p 8080:80 --name web-container web-devops-app'
            }
        }
    }
}