pipeline {
  agent any
    environment {
    SVC_ACCOUNT_KEY = credentials('terraform-auth')
  }
  stages{
    stage('Checkout') {
      steps {
        checkout scm
        sh 'echo $SVC_ACCOUNT_KEY | base64 -d > cread.json'
      }
    }
	stage('TF Plan') {
       steps {
         
           terraform init
		  }
		  steps{
           terraform plan 
         }
       }
   
	
	stage('TF Apply') {
      steps {
       
          terraform apply 
       
      }
    }
	}
  }

