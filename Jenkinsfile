pipeline{
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                  sh 'docker build -t viraj5132/nodejsapp-1.0:latest .'
                }
            }
        }
        stage('Deploy Docker Image') {
            steps {
                script {
               //  withCredentials([string(credentialsId: 'dockerhub-pwd', variable: 'dockerhubpwd')]) {
                    sh 'docker login -u viraj5132 -p Virajpatel#123'
                 }  
                 sh 'docker push viraj5132/nodejsapp-1.0:latest'
            }
        }
    
    }
}