pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                bat 'python name.py'
            }
        }
        stage('Result'){
            steps{
                echo 'The last build was successful'
            }
        }
        stage('checking'){
            steps{
                echo 'hii'
            }
        }
    }
}
