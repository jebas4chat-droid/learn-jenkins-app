pipeline {
    agent any

    stages {
        stage('Without docker') {
            steps {
                sh '''
                    echo "Hello World"
                    ls -la
                    touch docker-no.txt
                '''
            }
        }
        
        stage('with docker') {
            agent{
                docker {
                    image 'node:26.13.0-alpine3.24'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "With docker"
                    ls -la
                    touch docker-yes.txt
                '''
            }
        }
    }
}
