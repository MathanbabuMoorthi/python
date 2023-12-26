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
        post {
            always {
                emailext body: 'The build status is success', subject: 'Build Status', to: 'mr.mathan5555@gmail.com'
                )
            }
        }
    }
}
