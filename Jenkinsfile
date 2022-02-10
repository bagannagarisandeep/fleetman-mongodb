pipeline {
   agent any

   environment {
     // You must set the following environment variables
     // ORGANIZATION_NAME
     // YOUR_DOCKERHUB_USERNAME (it doesn't matter if you don't have one)
     
     ORGANIZATION_NAME = "bagannagarisandeep" 
     SERVICE_NAME = "fleetman-mongodb"
    
    // REPOSITORY_TAG ="${ECR_URI}:${BUILD_ID}"
   }

   stages {
      stage('Preparation') {
         steps {
            cleanWs()
            git credentialsId: 'GitHub', url: "https://github.com/${ORGANIZATION_NAME}/${SERVICE_NAME}"
         }
      }
       stage('Build') {
         steps {
            sh '''echo No build required for Mongodb'''
         }
      }

      stage('Build and Push Image') {
	      steps {		
	         sh 'echo No docker image for Mongodb'
         }
      }
	   
stage('Deploy to Cluster') {
     steps {
	sh 'envsubst < ${WORKSPACE}/deploy.yaml | /usr/local/bin/kubectl --kubeconfig ${WORKSPACE}/jenkins-cluster-admin-config apply -f -'
            }
	   }
	  }
         }
