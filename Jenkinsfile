pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the GitHub repository
                git branch: 'main', url: 'https://github.com/hoverhawk79/Jenkins-gs-spring-boot.git'
            }
        }

        stage('Build') {
            steps {
                // Run your build steps, e.g., compiling code or running tests
                sh 'echo Building...'
            }
        }

        stage('Test') {
            steps {
                // Run tests
                sh 'echo Testing...'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the application
                sh 'echo Deploying...'
            }
        }
    }
}
