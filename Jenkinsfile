pipeline {
    agent any

    stages {
        stage('Cloning github repository') {
            steps {
                git 'https://github.com/nandithamgowda48-dev/static-web-hosting-dockerfile.git'
            }
        }
        stage('Building Image') {
            steps {
                bat 'docker build -t jenkins-docker .'
            }
        }
        stage('Creating container') {
            steps {
                bat 'docker run -d -p 120:80 --name jenkins-docker8 jenkins-docker'
            }
        }
        stage('Pushing image to dockerhub') {
            steps {
                bat '''docker login -u nanditham -p Nanditha@123
                docker tag jenkins-docker nanditham/jenkins-docker:v1
                docker push nanditham/jenkins-docker:v1'''
            }
        }
        
    }
}
