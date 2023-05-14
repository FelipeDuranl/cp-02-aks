pipeline {
  agent any
  
  stages {
    stage('Checkout') {
      
    }
    
    stage('Build') {
      steps {
        sh 'npm install'  // Instalar as dependências do Node.js
      }
    }
    
    stage('Deploy to AKS') {
      environment {
        KUBECONFIG = credentials('clusterUser_cp-02_aks-jenkins')
      }
      steps {
        sh 'kubectl apply -f path/to/kubernetes/manifest.yaml'
      }
    }
    
    stage('Start Node.js Application') {
      steps {
        sh 'npm start'  // Iniciar o servidor Node.js
      }
    }
  }
}
