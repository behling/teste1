pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    options {
        timeout(time: 30, unit: 'SECONDS') 
    }
    
    parameters {
        string(name: 'DEV', defaultValue: 'Jenkins', description: 'Test')
        choice(name: 'DEV_TO', choices: "development\nproduction", description: 'Deploy to ...')
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
            when { environment name: 'DEV_TO', value: 'production' }
            steps {
                echo 'Choise....'
            }
        }
    }
}
