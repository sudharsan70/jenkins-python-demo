pipeline {
    agent {
        docker {
            image 'python:3.11-slim'
            args '-u root'
        }
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh '''
                pip install --upgrade pip
                pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest -v'
            }
        }
    }
}