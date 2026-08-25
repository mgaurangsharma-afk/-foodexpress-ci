pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat '"C:\\Users\\Gaurang\\anaconda3\\python.exe" -m pip install pytest'
            }
        }

        stage('Test') {
            steps {
                bat '"C:\\Users\\Gaurang\\anaconda3\\python.exe" -m pytest'
            }
        }
    }
}