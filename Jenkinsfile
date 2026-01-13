pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                echo 'Checking out source code...'
            }
        }

        stage('Build with Maven') {
            steps {
                echo 'Building application...'
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Unit Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
