pipeline {
    agent any

    environment {
        PROJECT_NAME = "E-commerce-project-springBoot"
        GITHUB_REPO_URL = "https://github.com/shaikimranmr/working1995.git"
    }

    stages {
        stage('Checkout') {
            steps {
                git url: "${GITHUB_REPO_URL}", branch: 'main'
            }
        }

        stage('Build') {
            steps {
                dir('JtProject') {
                    sh 'mvn clean package -DskipTests'
                }
            }
        }

        stage('Test') {
            steps {
                dir('JtProject') {
                    sh 'mvn test'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy logic goes here'
                // Add deployment steps here, if needed
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed!'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        always {
            cleanWs()
        }
    }
}
