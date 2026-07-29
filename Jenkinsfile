pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/shyampuli/dynamic-website.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-dynamic-app .'
            }
        }
        stage('Push to Registry') {
            steps {
                sh 'docker tag my-dynamic-app shyamprasad2310/my-dynamic-app:latest'
                sh 'docker push shyamprasad2310/my-dynamic-app:latest'
            }
        }
    }
}
