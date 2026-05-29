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
                bat 'docker build -t ci-node-web-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
               
                bat 'docker run -d -p 3000:3000 --name web-container ci-node-web-app'
            }
        }
    }
}