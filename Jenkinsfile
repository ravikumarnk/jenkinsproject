pipeline {
    agent any

    tools {
        // optional: the name you give Maven in Manage Jenkins -> Global Tool Configuration
        // If you don't configure this, ensure 'mvn' is on the Windows PATH of your agent.
        // maven 'Maven3'
    }

    stages {
        stage('Test') {
            steps {
                echo 'Running unit tests...'
                // use bat for Windows agents
                bat 'mvn -B test'
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
                bat 'mvn -B -DskipTests=true package'
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
                // Example: bat 'scp target\\myapp.jar user@server:/opt/apps/' (if scp available)
            }
        }
    }

    post {
        success { echo "Pipeline SUCCESS" }
        failure { echo "Pipeline FAILED — check console output" }
    }
}
