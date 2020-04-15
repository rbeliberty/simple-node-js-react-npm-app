pipeline{
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000 -u 106:112'
        }
    }
    environment {
        HOME = '.'
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test'){
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver'){
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the website ? (click "Proceed" tot continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }

}