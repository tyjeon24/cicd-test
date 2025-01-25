pipeline {
    agent {
        docker {
            image 'python:3.13.1'
        }
    }
    stages {
        stage('Check Python') {
            steps {
                sh 'python --version'
            }
        }
    }
}
