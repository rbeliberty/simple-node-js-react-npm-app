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
    }

}