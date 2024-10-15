pipeline {
    agent any

    tools {
        maven 'Maven_3.9.9' // 使用你配置的 Maven 版本
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the GitHub repository
                git branch: 'main', url: 'https://github.com/hoverhawk79/Jenkins-gs-spring-boot.git'
            }
        }

        stage('Build and Test') {
            steps {
                dir('initial') { // 确保 'initial' 目录是项目中实际包含 pom.xml 的位置
                    // Run build
                    sh 'mvn clean install'

                    // Run unit tests
                    sh 'mvn test'

                    // Run integration tests
                    sh 'mvn verify'
                }
            }
        }

        // SonarQube Analysis: 解开注释以启用代码分析
        /*
        stage('SonarQube Analysis') {
            steps {
                dir('initial') {
                    withCredentials([string(credentialsId: 'SQ_token', variable: 'SONAR_TOKEN')]) {
                        withSonarQubeEnv('SonarQube') {
                            sh "mvn sonar:sonar -Dsonar.login=$SONAR_TOKEN"
                        }
                    }
                }
            }
        }
        */

        stage('Deploy') {
            steps {
                // 假设部署在本地或远程服务器
                sh 'echo Deploying...'
            }
        }
    }
}
