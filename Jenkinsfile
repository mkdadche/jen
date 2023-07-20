pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                git url: 'https://github.com/mkdadche/jen', branch: 'main', credentialsId: 'github-credentials'
            }
        }

        stage('Build') {
            steps {
                // Install Python dependencies
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                // Run tests for the Flask app
                sh 'python -m unittest discover tests'
            }
        }

        stage('Run Flask App') {
            steps {
                // Run the Flask app
                sh 'python app.py'
            }
        }
    }
}

