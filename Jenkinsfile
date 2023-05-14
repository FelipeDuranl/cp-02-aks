pipeline {
    agent any
    
    tools {
        nodejs 'Nome_da_Instalação_do_NodeJS'
    }
    
    stages {
        
        stage('Install') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        
        stage('Deploy to AKS') {
            steps {
                sh 'kubectl apply -f path/to/kubernetes/manifest.yaml'
            }
        }
    }
}
