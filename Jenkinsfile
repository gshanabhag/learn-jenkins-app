pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine' //docker image
                    reuseNode true //reuses the same workspace for all stages
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci #run build
                    npm run build
                    ls -la
                '''
            }
        }
    }
}