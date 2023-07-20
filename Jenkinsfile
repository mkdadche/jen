pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                git url: 'https://github.com/mkdadche/jen', branch: 'main', credentialsId: 'github-credentials'
            }
        }

        stage('Build and Test') {
            steps {
                // Install Python and run the Flask app
                sh 'python app.py'
            }
        }
    }
}
