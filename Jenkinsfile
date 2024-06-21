pipeline {
    agent any

    stages {
        stage("First build") {
            steps{
            sh 'npm install'
            }
        }
        stage ("Test") {
            steps {
                sh 'npm test'
            }
        }
        stage ("Build") {
            steps {
                sh 'npm run build'
            }
        } 
    }
}
