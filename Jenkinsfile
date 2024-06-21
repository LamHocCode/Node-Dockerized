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
        stage ("Build Image") {
            steps {
                sh 'docker build -t node-dockerized:1.0 .'
            }
        }
        stage("Docker Push") {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'DOCKERHUB_USERNAME', passwordVariable: 'DOCKERHUB_PASSWORD')]) {
                    sh 'docker login -u $DOCKERHUB_USERNAME -p $DOCKERHUB_PASSWORD'
                    sh 'docker tag node-dockerized:1.0 lamhoccode/node-dockerized:1.0'
                    sh 'docker push lamhoccode/node-dockerized:1.0'
                    sh 'docker logout'
                }
            }
        }
    }
}
