pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Running unit tests...'
                sh 'mvn -B test'
            }
            post {
                always {
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }

        stage('Build') {
            steps {
                echo 'Building the app (package)...'
                sh 'mvn -B -DskipTests=true package'
            }
            post {
                success {
                    archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy step (placeholder) - implement your deploy here'
                // Example: sh "scp target/myapp.jar user@server:/opt/apps/"
            }
        }
    }

    post {
        success { echo "Pipeline completed SUCCESS" }
        failure { echo "Pipeline FAILED — check console output" }
    }
}
