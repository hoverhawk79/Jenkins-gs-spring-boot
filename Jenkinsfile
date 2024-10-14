pipeline {
    agent any

    tools {
        maven 'Maven_3.9.9'
    }
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
                dir('initial') { // 修改为你的 pom.xml 文件所在的目录
                    sh 'mvn clean install'
                }
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
