pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-dynamic-app .'
            }
        }

        stage('Push to Registry') {
            steps {
                bat 'docker tag my-dynamic-app shyamprasad2310/my-dynamic-app:latest'
                bat 'docker push shyamprasad2310/my-dynamic-app:latest'
            }
        }
    }
}
