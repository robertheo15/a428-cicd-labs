pipeline {
        agent {
            docker {
                image 'python:latest'
                args '-p 3000:3000'
            }
        }
        stages {
            stage('Python version: ') {
                steps {
                    sh 'python3 --version'
                }
            }
            stage('Running python script:') { 
                steps {
                    sh 'python3 main.py'
                }
            }
        }
    }