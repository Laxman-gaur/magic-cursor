pipeline {
    agent any
    stages {
        stage('change directory and present working directory') {
            steps {
                sh 'cd /home/ubuntu'
                sh 'pwd'
            }
        }
        stage('Clone') {
            steps {
                sh 'git clone https://github.com/Laxman-gaur/magic-cursor.git'
            }
        }
        stage('build') {
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
                sh 'npm start server.js'
            }
        }
    }
}
