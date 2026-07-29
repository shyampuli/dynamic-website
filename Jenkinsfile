pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat '"C:\\Users\\pulis\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" build -t my-dynamic-app .'
            }
        }

        stage('Push to Registry') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', usernameVariable: 'shyamprasad2310', passwordVariable: 'Prasadpuli231@')]) {
                    bat '''
                        "C:\\Users\\pulis\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" login -u %DOCKER_USER% -p %DOCKER_PASS%
                        "C:\\Users\\pulis\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" tag my-dynamic-app shyamprasad2310/my-dynamic-app:latest
                        "C:\\Users\\pulis\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" push shyamprasad2310/my-dynamic-app:latest
                    '''
                }
            }
        }
    }
}
