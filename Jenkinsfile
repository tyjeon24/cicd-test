pipeline {
    agent {
        docker {
            image 'python:3.10'
        }
    }
    stages {
        stage('Checkout Code') {
            steps {
                checkout scm  // Pull code from Git repository
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'  // Install Python packages
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
