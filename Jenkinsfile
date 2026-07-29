pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/YOURNAME/dynamic-website.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-dynamic-app .'
            }
        }
        stage('Push to Registry') {
            steps {
                sh 'docker tag my-dynamic-app YOUR_DOCKERHUB/my-dynamic-app:latest'
                sh 'docker push YOUR_DOCKERHUB/my-dynamic-app:latest'
            }
        }
    }
}
