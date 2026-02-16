
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
                bat 'mv n -B package'
            }
             
        }


        stage('Deploy') {
    steps {
        
        echo "Deploying application..."
    }
    post {
        success {
            emailext (
                subject: "Deployment SUCCESS",
                body: "Application deployed successfully.\nBuild: ${env.BUILD_URL}",
                to: "ravikelakam@gmail.com"
            )
        }
    }
}


        
    }

    post {
        success { echo "Pipeline SUCCESS" }
        failure { echo "Pipeline FAILED" }
    }
}
