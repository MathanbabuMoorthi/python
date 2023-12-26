pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'python name.py'
            }
        }

        stage('Result') {
            steps {
                echo 'The last build was successful'
            }
        }

        stage('Testing') {
            steps {
                bat 'python name.py'
            }
        }
    }

    post {
        always {
            emailext(
                subject: 'Build Status',
                body: 'The build status is successful.',
                to: 'mr.mathan5555@gmail.com',
                attachLog: true
            )
        }
    }
}
