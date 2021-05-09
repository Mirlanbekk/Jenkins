pipeline {
    agent any
     parameters {
        string(name: 'Terraform Command', defaultValue: 'apply', description: 'Which terraform command would you like to use?')
    }
    environment {
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
    }
    stages {
        stage('Terraform Init') {
            steps {
                sh '''
                   cd Infrastructure/
                   terraform init
                   terraform ${params.Terraform-Command} -auto-approve
                '''
            }
        }
       
    }
}
