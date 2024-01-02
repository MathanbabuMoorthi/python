pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                bat 'python3 ops.py'
            }
        }
        stage(test){
            steps{
                bat 'python3 -m pytest'
            }
        }
    }
}