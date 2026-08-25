pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat '"C:\\Users\\Gaurang\\anaconda3\\python.exe" -m venv venv'
                bat 'venv\\Scripts\\python.exe -m pip install pytest flake8'
            }
        }

        stage('Code Quality') {
            steps {
                bat 'venv\\Scripts\\flake8.exe cart.py orders.py || exit /b 0'
            }
        }

        stage('Test') {
            steps {
                bat 'venv\\Scripts\\python.exe -m pytest'
            }
        }

        stage('Package') {
            steps {
                bat 'venv\\Scripts\\python.exe package.py'
                archiveArtifacts artifacts: 'foodexpress.zip', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: all stages passed and the artifact was created.'
        }

        failure {
            echo 'FAILURE: one stage failed. Open the red stage to see why.'
        }
    }
}