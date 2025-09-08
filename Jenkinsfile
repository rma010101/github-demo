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
    }
}
