#!groovy
def aws = new io.ouicar.aws()
def compose = new io.ouicar.compose()
def docker = new io.ouicar.docker()
def git = new io.ouicar.git()
def terraform = new io.ouicar.terraform()

pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000'
        }
    }
    environment { 
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Deploy to Sendgrid') {
            steps {
                sh 'npm run deploy'
            }
        }
    }
}