pipeline {
    agent any
    stages {
            stage('Checkout') {
                steps {
                    sh 'git https://github.com/bibash2052/docker-compose-nginx-phpfpm'
                }
            }
            stage('Build Docker Image') {
                steps {
                    sh 'docker build -t php-jenkins-deploy .'
                }
            }
            stage('Deploy Docker Image') {
                steps {
                    sh 'docker run -d -p 8811:80 php-jenkins-deploy:latest'
                }
            }
        }
  }