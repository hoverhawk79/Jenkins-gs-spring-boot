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

        stage('Unit Tests') {
            steps {
                dir('initial') { // 修改为你的 pom.xml 文件所在的目录
                sh 'mvn test'
                }
            }
        }
        stage('Integration Tests') {
            steps {
                dir('initial') { // 修改为你的 pom.xml 文件所在的目录
                sh 'mvn verify'
                }
            }
        }
        stage('SonarQube Analysis') {
            steps {
                dir('initial') { // 修改为你的 pom.xml 文件所在的目录
                   withSonarQubeEnv('SonarQube') {
                   sh 'mvn sonar:sonar -Dsonar.host.url=http://192.168.1.73:9000'
                   }
                }
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
