pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                bat 'python ops.py'
            }
        }
        stage('test'){
            steps{
                script{
                    bat 'python -m unittest discover -p "*test_ops.py"'
                }
            }
        }
    }
    post{
        always{
            script{
                junit 'test_result.xml'
            }
        }
    }
}