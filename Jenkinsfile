pipeline {
  agent any
  
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/FelipeDuranl/cp-02-aks.git'
      }
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
