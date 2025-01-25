/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'python:3.13.1-alpine3.21' } }
    stages {
        stage('test') {
            steps {
                echo 'Hello, Jenkins!'
            }
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
    }
}
