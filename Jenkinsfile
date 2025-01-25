pipeline {
    agent { 
        docker { 
            image 'python:3.13.1' 
        } 
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello, World!'
            }
        }
        stage('Build') {
            steps {
                sh 'python --version'
            }
        }
    }
}
