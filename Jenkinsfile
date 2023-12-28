pipeline {
    agent any

    environment {
        VENV = 'venv'
    }

    stages {
        stage('Install Requirements') {
            steps {
                script {
                    bat "python -m venv ${VENV}"
                    bat ".\\${VENV}\\Scripts\\activate"
                    bat "pip install -r requirements.txt"
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    bat "pytest mytests/test_sets.py --junitxml=TEST-junit.xml"
                }
            }
        }

        stage('Result') {
            steps {
                echo "The test is a success"
            }
        }
    }

    post {
        always {
            junit 'TEST-junit.xml'
        }
    }
}
