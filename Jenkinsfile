pipeline {
  agent { label 'master' }
  
  tools {
        maven 'mvn-11'
        jdk 'jdk-11' 
  }
  
   stages {
      stage('Hello') {
          steps {
              echo "Hello World!"
            bat 'dr'
          }
      }
     
     
     stage('Code Checkout') {
          steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'GITHUB_credentials', url: 'https://github.com/sachkale/Python.git']]])
          }
      }
     
    
       
   }
   }
