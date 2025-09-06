pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh '''
                echo "Without Docker"
                ls -la
                touch containers-no.txt
                '''
            }
        }
        
         stage('w/ docker') {
                         agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh '''
                echo "With docker"
                ls -la
                touch containers-yes.txt
                '''
            }
        }
    }
}
