pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh '''
                    echo "Without docker"
                    ls -la
                    touch container-no.txt
                '''
            }
        }
        stage('w/ docker') {
            agent {
                docker {
                    image 'node:18-alpine' // Specify the Docker image
                }
            }
            steps {
                sh '''
                    echo "With docker" // Fixed shell command
                    ls -la
                    touch container-yes.txt
                '''
            }
        }
    }
}