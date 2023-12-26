pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                git branch: 'python', url: 'https://github.com/MathanbabuMoorthi/python.git'
                bat 'python name.py'
            }
        }
    }
}
