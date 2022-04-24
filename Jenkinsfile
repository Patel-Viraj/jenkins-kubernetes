pipeline{
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                script {
             //     sh 'docker build -t viraj5132/nodejsapp-1.0:latest .'
                }
            }
        }
        stage('Deploy Docker Image') {
            steps {
                script {
         //           sh 'docker login -u viraj5132 -p Virajpatel#123'
                 }  
         //        sh 'docker push viraj5132/nodejsapp-1.0:latest'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sshagent(['3.91.222.148']) {
                     sh "scp -o StrictHostKeyChecking=no nodejsapp.yaml ubuntu@3.222.116.50:/home/ubuntu/kubernetes"
                     script {
                         try{
                             sh "ssh ubuntu@3.222.116.50 kubectl create -f /home/ubuntu/kubernetes/nodejsapp.yaml"
                         } catch(error){
                             sh "ssh ubuntu@3.222.116.50 kubectl create -f /home/ubuntu/kubernetes/nodejsapp.yaml"
                         }
                     }
                }
            }
        }
    
    }
}