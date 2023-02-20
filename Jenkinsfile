pipeline {
    agent any
    stages {
        stage('change directory and present working directory') {
            steps {
                sh 'cd /home/ubuntu/magic-cursor'
                sh 'pwd'
            }
        }
        stage('build') {
            steps {
                sh 'npm audit fix'
                sh 'npm install'
            }
        }
        stage ('approval') {
            input {
                message "do you want to proceed for production deployment ?"
            }
            steps {
                sh "deploy to production"
            }
        }
        stage('Deploy') {
            steps {
                sh 'npm start server.js'
            }
        }
    }
}
