pipeline {
    agent any
    
    stages {
        stage('Hello') {
            steps {
                echo 'Hello, World!'
            }
        }
        
        stage('Deploy to AKS') {
            steps {
                sh 'kubectl apply -f path/to/kubernetes/manifest.yaml'
            }
        }
    }
}
