pipeline {
    agent any

    parameters {
        choice(
            name: 'ENV',
            choices: ['dev', 'qa', 'prod'],
            description: 'Select deployment environment'
        )
    }

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
            post {
                success {
                    archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    if (params.ENV == 'dev') {
                        echo "Deploying to DEV environment"
                        // dev deployment logic
                    }
                    else if (params.ENV == 'qa') {
                        echo "Deploying to QA environment"
                        // qa deployment logic
                    }
                    else if (params.ENV == 'prod') {
                        echo "Deploying to PROD environment"
                        // prod deployment logic
                    }
                }
            }
        }
    }

    post {
        success {
            echo "Pipeline SUCCESS"
        }
        failure {
            echo "Pipeline FAILED"
        }
    }
}
