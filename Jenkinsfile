pipeline {
    agent {
        docker {
            image 'node:16-buster-slim' 
            args '-p 3000:3000' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm remove node_modules'
                sh 'npm remove package-lock.json'
                sh 'npm install' 
            }
        }
    }
}