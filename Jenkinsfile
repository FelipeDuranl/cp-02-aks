pipeline {
    agent any
    
    stages {
        stage('Hello') {
            steps {
                echo 'Hello, World!'
            }
        }
        
        stage('Deploy to AKS') {
          environment {
            KUBECONFIG = credentials('clusterUser_cp-02_aks-jenkins')
          }
          steps {
            sh 'kubectl apply -f manifest.yaml'
          }
        }
    }
}
