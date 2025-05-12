pipeline {
    agent any

    environment {
        MAVEN_OPTS = "-Dmaven.test.failure.ignore=false"
    }

    stages {
        stage('Checkout') {
            steps {
                // Replace with your repo URL
                git url: 'https://github.com/ravikumarnk/jenkinsproject.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                echo 'Running Maven Clean and Package...'
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Unit Tests...'
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Simulating deployment step...'
                // Add actual deployment logic here
                // Example: sh './deploy.sh' or call AWS CLI, SCP, etc.
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }
        failure {
            echo 'CI/CD Pipeline failed.'
        }
    }
}
