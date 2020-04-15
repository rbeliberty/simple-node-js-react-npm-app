pipeline{
    agent {
        docker {
            image 'node:12-alpine'
            args '-p 3000:3000 -u 106:112'


        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
    }
}