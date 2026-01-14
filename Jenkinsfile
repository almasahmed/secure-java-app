pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/almasahmed/secure-java-app.git'
            }
        }

        stage('Build') {
            steps {
                sh 'chmod +x mvnw'
                sh './mvnw clean package -DskipTests'
            }
        }

        stage('Unit Test') {
            steps {
                sh './mvnw test'
            }
        }
    }

    post {
        failure {
            echo 'CI Pipeline failed!'
        }
        success {
            echo 'CI Pipeline succeeded!'
        }
    }
}

