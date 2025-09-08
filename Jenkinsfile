pipeline {
    agent any

    stages {
        stage('Check Docker Version') {
            steps {
                // This command lists the files to verify they were checked out correctly
                bat 'docker--version'
            }
        }
        stage('Verify') {
            steps {
                // This command lists the files to verify they were checked out correctly
                bat 'dir'
            }
        }
        stage('Build Docker Image') {
            steps {
                // This command lists the files to verify they were checked out correctly
                bat 'docker build -t rma010101/github-demo.git'
            }
        }
        stage('Push Docker Image') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
                    bat 'docker login -u %DOCKER_USERNAME% -p %DOCKER_PASSWORD%'
                    bat 'docker push rma010101/github-demo.git'
                }
            }
        }
    }
}
