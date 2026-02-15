pipeline {
    agent any

    stages {

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                bat 'mvn -B test'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the app...'
                bat 'mvn -B package'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy step (placeholder)'
            }
        }
    }

    post {
        success { echo "Pipeline SUCCESS" }
        failure { echo "Pipeline FAILED" }
    }
}
