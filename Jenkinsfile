pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh '''cd ..
                      ls -alF'''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh '''cd ../exemplo-freestyle/
                      ls -alF'''
            }
        }
    }
}
