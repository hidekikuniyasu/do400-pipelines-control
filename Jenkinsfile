pipeline {
    agent {
        node {
            label 'nodejs'
        }
    }
    stages {
        stage('Backend Tests') {
            steps {
                sh 'node ./backend/test.js'
            }      
        }
        stage('Frontend Tests') {
            steps {
                sh 'node ./frontend/test.js'
            }
        }
        stage('Release') {
            steps {
                sh '''
                    oc project akibvl-greetings
                    oc start-build greeting-console --follow --wait
                '''
            }

        }
    }
}



