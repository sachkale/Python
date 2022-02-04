pipeline {
  agent any
  
 environment {

    PATH = "C:\\WINDOWS\\SYSTEM32"

}
 
   stages {
      stage('Hello') {
          steps {
              echo "Hello World!"
          }
      }
     
     
     stage('Code Checkout') {
          steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'GITHUB_credentials', url: 'https://github.com/sachkale/Python.git']]])
            bat 'dr'
            
          }
       
      }
    }
}
