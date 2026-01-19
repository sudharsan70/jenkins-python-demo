pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/sudharsan70/jenkins-python-demo.git'
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                python3 -m venv venv
                source venv/bin/activate
                pip install -r requirements.txt
                pytest -v
                '''
            }
        }
    }
}