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
                      cd ../../
                      ls -alF
                      cat credentials.xml
                      ls -alF .ssh/'''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh '''cd ../exemplo-freestyle/
                      ls -alF
                      cd /tmp/
                      ls -alF'''
            }
        }
        stage('Exec') {
            steps {
                echo 'Java....'
                sh '''cd /tmp/
                      java -jar winstone5045359224069363457.jar'''
            }
        }
    }
}
