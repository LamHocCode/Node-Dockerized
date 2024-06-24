pipeline {
    agent any

    stages {
        stage("First initialize") {
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
        stage ("Build Image") {
            steps {
                sh 'docker build -t lamhoccode/node-dockerized:2.0 .'
            }
        }
        stage("Docker Push") {
            steps {
                withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/')  {
                    sh 'docker push lamhoccode/node-dockerized:2.0'
                }
            }
        }
    }
}
