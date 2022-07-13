pipeline {
    agent any
    parameters {
        string(name: 'project_name', defaultValue: 'Packer Pipeline', description: 'Jenkins Pipeline for terraform?')
    }
    environment {
        terraform_version = '0.11.11'
        packer_version = '1.4.3'
    }
    stages {
          stage('code checkout') {
               steps {
                      git branch: 'main', credentialsId: '5fd8f57f-4320-4a5e-801d-320dd523aec7', url: 'https://github.com/Patlollavinod/TPJ_jenkins.git'
                    }
          }
          stage('Install Terraform') {
              steps {
                    sh "sudo apt-get update && sudo apt-get install terraform"
                    sh "sudo terraform version"
              }
          }
          stage('Install Packer') {
              steps {
                    sh "sudo apt-get update && sudo apt-get install packer"
                    sh "sudo packer version"
              }
          }
     } 
}   
