pipeline {
    agent any

    stages {

        stage('Test') {
            steps {
                bat 'mvn -B test'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn -B package'
            }
             
        }

        stage('Deploy') {
            steps {
                echo "Deploy step"
            }
        }
    }

    post {
        success { echo "Pipeline SUCCESS" }
        failure { echo "Pipeline FAILED" }
    }
}
