pipeline {
    agent {
        docker {
            image 'python:3.10'
            args '-e HOME=/root -v $HOME/.cache/pip:/root/.cache/pip'
        }
    }
    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'pip install --no-cache-dir -r requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'pytest --junitxml=test-results.xml'  // Run tests with JUnit report
            }
        }
    }
    post {
        always {
            junit 'test-results.xml'  // Publish test results in Jenkins UI
        }
        failure {
            echo "Tests failed! Check the test report."
        }
    }
}
