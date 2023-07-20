pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                git url: , branch: 'main', credentialsId: 'github-credentials'
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
        // Install Python dependencies
        sh 'pip install -r requirements.txt'
        
        // Run tests for the Flask app and generate JUnit test reports
        sh 'python -m unittest discover -v -s tests -p "test_*.py" -b --junitxml=tests/test-results.xml'
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

