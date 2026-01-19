pipeline {
    agent any

    environment {
        VENV = 'venv'
    }

    stages {
        stage('Setup Environment') {
            steps {
                sh '''
                python3 -m venv $VENV
                source $VENV/bin/activate
                pip install --upgrade pip
                pip install -r requirements.txt
                '''
            }
        }

        stage('Run Unit Tests') {
            steps {
                sh '''
                source $VENV/bin/activate
                pytest -v --junitxml=report.xml
                '''
            }
        }
    }

    post {
        always {
            junit 'report.xml'
        }
        success {
            echo 'Build passed. Tests successful.'
        }
        failure {
            echo 'Build failed. Fix the tests.'
        }
    }
}