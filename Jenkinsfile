pipeline {
    agent any
    stages {
        stage('change directory and present working directory') {
            steps {
                sh 'cd /var/lib/jenkins/workspace'
                sh 'git clone https://github.com/Laxman-gaur/magic-cursor.git'
                sh 'cd ./magic-cursor'
                sh 'pwd'
            }
        }
        stage('install required dependencies') {
            steps {
                sh 'npm audit fix --force'
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
        stage('deploy') {
            steps {
                sh 'pm2 start server.js'
            }
        }
    }
}
