pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Poll SCM and checkout the GitHub repository
                git 'https://github.com/your-username/your-repository.git'
            }
        }
        
        stage('Terraform Destroy') {
            steps {
                // Run Terraform destroy
                script {
                    sh 'terraform init'
                    sh 'terraform destroy -auto-approve'
                }
            }
        }

        stage('Terraform Apply') {
            steps {
                // Run Terraform apply
                script {
                    sh 'terraform init'
                    sh 'terraform apply -auto-approve'
                }
            }
        }
    }
}