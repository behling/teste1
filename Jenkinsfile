pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }
    
    parameters {
        string(name: 'DEV', defaultValue: 'Jenkins', description: 'jenkinsfile')
        choise(name: 'DEV_TO', coises: 'development\nproduction', description: 'Deploy to ...')
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
        stage('Deploy Choise') {
            when { enviroment name: 'DEV_TO', value: 'production'}
            steps {
                echo 'Choise....'
            }
        }
    }
}
