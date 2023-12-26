pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                git branch: 'python', url: 'https://github.com/MathanbabuMoorthi/python.git'
                bat 'python name.py'
            }
        }
        stage('Result'){
            steps{
                echo 'The last build was successful'
            }
        }
    }
}
