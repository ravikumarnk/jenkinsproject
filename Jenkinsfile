pipeline {
    agent any

    stages {
        stage('Debug') {
            steps {
                sh 'git status'
                sh 'git branch -a'
                sh 'ls -la'
            }
        }
        stage('Build') {
            steps {
                echo 'Building my Maven app...'
                sh 'mvn clean install'
            }
        }
    }
}
