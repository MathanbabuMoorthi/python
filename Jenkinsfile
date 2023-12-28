pipeline {
    agent any

    environment {
        WORKSPACE = 'workspace'
        VENV = 'venv'
    }

    stages {
        stage('Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Install Requirements') {
            steps {
                script {
                    bat "mkdir ${WORKSPACE}"
                    currentBuild.workspace = "${WORKSPACE}"
                    bat "python -m venv ${VENV}"
                    bat ".\\${VENV}\\Scripts\\activate"
                    bat "pip install -r requirements.txt"
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    bat ".\\${VENV}\\Scripts\\activate && pytest mytests --junitxml=TEST-junit.xml"
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
