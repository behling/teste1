pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }
    
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh '''pwd
                      cd ..
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
