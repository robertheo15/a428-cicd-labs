node {
    docker.image('node:16-buster-slim').run('-p 3000:3000') {
        stage('Build') {
            try {
                sh 'npm install'
            } catch (Exception e) {
                currentBuild.result = 'FAILURE'
                throw e
            }
        }
    }
}