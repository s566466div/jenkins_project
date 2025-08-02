pipeline {
    agent any

    tools {
        jdk 'Java 11'
        maven 'Maven 3.8.1'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/s566466div/jenkins_project.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo '✅ Build and tests passed!'
        }
        failure {
            echo '❌ Build or tests failed.'
        }
    }
}
