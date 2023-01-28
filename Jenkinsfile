pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t dab8106/pythonapp28012023 .'
            }
        }
        stage('Push') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
                    sh "docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD"
                    sh 'docker push dab8106/pythonapp28012023'
                }
            }
        }
    }
}
