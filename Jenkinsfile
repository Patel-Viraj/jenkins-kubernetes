pipeline{
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                sh "echo staring build the image"
                script {
                    sh 'docker build -t viraj5132/nodejsapp-1.0:latest .'
                }
            }
        }
        stage('Deploy Docker Image') {
            steps {
                sh "echo staring deploy the image"
                script {
                    sh 'docker login -u viraj5132 -p Virajpatel#123'
                }  
                sh 'docker push viraj5132/nodejsapp-1.0:latest'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sshagent(['3.91.222.148']) {
                    sh "echo staring deploy the image"
                    sh "scp -o StrictHostKeyChecking=no nodejsapp.yaml ubuntu@3.80.10.99:/home/ubuntu/"
                     script {
                              sh "ssh ubuntu@3.80.10.99 kubectl apply -f nodejsapp.yaml" 
                     }
                }
            }
        }
    
    }
}
