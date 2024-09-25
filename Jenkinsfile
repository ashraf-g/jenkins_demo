pipeline{
    agent any
    stages{
        stage('Clone repo')
        {
            steps{
                git branch:'main',url:'https://github.com/ashraf-g/jenkins_demo.git'
            }
        }
        stage('install Dependencies')
        {
            steps{
                // sh is used to run file in terminal
                sh 'npm install'
            }   
        }
        stage('Testing application') {
            steps{
                sh 'npm test'
            }
        }
        stage('Start application'){
            input{
                message 'Do you really want to start?'
                ok 'clidk on ok'
                submitter 'Groot'
            }
            steps{
                sh 'npm start'
            }
        }
    }
}