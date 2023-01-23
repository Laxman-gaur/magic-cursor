pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/Laxman-gaur/flask-calculator.git', branch: 'main'
            }
        }
        stage('change directory') {
            steps {
                sh 'cd /home/ubuntu/flask-calculator'
            }
        }
        stage('present working directory') {
            steps {
                sh 'pwd'
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'pm2 start server.js'
            }
        }
    }
}
