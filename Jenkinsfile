pipeline {
    stages {
        stage('build') {
            agent {
                docker {
                    image 'node:26-slim'
                    reuseNode true
                }
            }
            steps {
                echo 'building...'
                sh '''
                    npm --version
                    node --version
                    npm ci
                    npm run build
                    '''
                    }
        }
    }
}