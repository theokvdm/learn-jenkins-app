pipeline {
    agent any
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
        stage('test') {
            agent {
                docker {
                    image 'node:26-slim'
                    reuseNode true
                }
            }
            steps {
                echo 'testing...'
                sh '''
                    sh 'test -f build/index.html'
                    '''
            }
        }
    }
}