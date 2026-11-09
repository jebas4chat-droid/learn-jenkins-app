pipeline {
    agent any
    stages {               
        stage('build') {
            agent{
                docker {
                    image 'node:26.13.0-alpine3.24'
                    reuseNode true
                }
            }
            steps {
                sh '''                    
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}
