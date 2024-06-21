pipeline {
    agent any

    stages {
        stage ('Checkout') {
            steps {
                checkout scm
            }
        }
        stage ("Build") {
            steps {
                sh 'npm run install'
            }
        } 
        stage ("Test") {
            steps {
                sh 'npm test'
            }
        }
        stage ("Deploy") {
            steps {
                sh 'npm run build'
                sh 'npm start'
            }
        }

    }
}
