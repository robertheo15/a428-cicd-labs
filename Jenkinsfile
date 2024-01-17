node {
    docker.image('python:latest').inside('-p 3000:3000') {
        stage('Build') {
            try {
                sh 'python3 main.py sdist'
            } catch (Exception e) {
                currentBuild.result = 'FAILURE'
                throw e
            }
        }
        stage('Test') {
            try {
                sh 'python3 main.py'
            } catch (Exception e) {
                currentBuild.result = 'FAILURE'
                throw e
            }
        }
        stage('Deploy') {
            try {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Sudah selesai menggunakan Python App? (Klik "Proceed" untuk mengakhiri)'
                sh './jenkins/scripts/kill.sh'            
            } catch (Exception e) {
                currentBuild.result = 'FAILURE'
                throw e
            }
        }
    }
}