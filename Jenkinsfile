node {
    docker.image('node:16-buster-slim').inside('-p 3000:3000') {
        stage('Build') {
            try {
                sh 'npm install'
            } catch (Exception e) {
                currentBuild.result = 'FAILURE'
                throw e
            }
        }
        stage('Test') {
            try {
                sh './jenkins/scripts/test.sh' 
            } catch (Exception e) {
                currentBuild.result = 'FAILURE'
                throw e
            }
        }
        stage('Deploy') {
            try {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Sudah selesai menggunakan React App? (Klik "Proceed" untuk mengakhiri)'
                sh './jenkins/scripts/kill.sh'
            } catch (Exception e) {
                currentBuild.result = 'FAILURE'
                throw e
            }
        }

    }
}