// pipeline {
//     agent any

//     stages {

//         stage('Clone Repository') {
//             steps {
//                 git branch: 'main',
//                 url: 'https://github.com/useradmin331/ci-web-node-app.git'
//             }
//         }

//         stage('Build Docker Image') {
//             steps {
//                 bat 'docker build -t ci-node-web-app .'
//             }
//         }

//         stage('Run Docker Container') {
//             steps {
               
//                 bat 'docker run -d -p 3000:3000 --name web-container ci-node-web-app'
//             }
//         }
//     }
// }




pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main',
                url: 'https://github.com/useradmin331/ci-web-node-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run Application') {
            steps {
                bat 'node app.js'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t ci-node-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker rm -f ci-container'
                bat 'docker run -d -p 3000:3000 --name ci-container ci-node-app'
            }
        }
    }
}