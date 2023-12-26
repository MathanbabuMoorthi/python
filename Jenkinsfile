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
        stage('Testing'){
            steps{
                   bat 'start python name.py'
            }
        }
} 
     post {
        always {
            emailext(
                subject: 'Build Successful',
                body: 'The build was successful. Good job!',
                recipientProviders: [mathan7112@gmail.com],
                attachLog: true,
            )
        }
}
