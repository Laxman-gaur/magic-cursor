pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/Laxman-gaur/magic-cursor.git', branch: 'master'
            }
        }
        stage('change directory and present working directory') {
            steps {
                sh 'cd /home/ubuntu/magic-cursor'
                sh 'pwd'
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm test'
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
                sh 'pm2 start server.js'
            }
        }
    }
}
