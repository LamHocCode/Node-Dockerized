pipeline {
    agent any

    stages {
        stage ("Test") {
            steps {
                sh 'npm install'
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
