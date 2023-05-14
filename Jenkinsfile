pipeline {
    agent any
    
    tools {
        kubernetesCli 'kubectl'
    }
    
    stages {
        
        stage('Build') {
          steps {
            // Instalar dependências e compilar o projeto
            sh 'npm install'
            sh 'npm run build'
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
