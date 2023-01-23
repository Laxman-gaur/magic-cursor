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
                sh 'cd /home/ubuntu'
                sh 'pwd'
            }
        }
        stage('install required dependencies') {
            steps {
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
                sh 'pm2 start server.js'
            }
        }
    }
}
