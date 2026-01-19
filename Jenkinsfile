pipeline {
    agent any

    stages {
        stage('Run Tests in Docker') {
            steps {
                sh '''
                docker run --rm \
                  -v "$PWD":/app \
                  -w /app \
                  python:3.11-slim \
                  sh -c "pip install -r requirements.txt && pytest -v"
                '''
            }
        }
    }
}