pipeline {
    agent any
    stages {
        stage('clone') {
            steps {
                url : https://github.com/useradmin331/ci-web-node-app.git
            }
        }
        stage('install') {
            steps {
                npm install
            }
        }
        stage('Deploy') {
            steps {
                npm start
                
            }
        }
    }
}