pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello, World!'
            }
        }
    }
    agent { docker { image 'python:3.13.1-alpine3.21' } }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
    }
}
