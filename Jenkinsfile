pipeline{
    agent {
        docker {
            image 'node:12-alpine'
            args '-p 3000:3000'
            args '-v $HOME/.npm:/root/.npm'
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