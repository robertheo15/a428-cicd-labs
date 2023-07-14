pipeline {
    agent {
        docker {
            image 'node:16-buster-slim' 
            args '-p 5173:5173' 
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
