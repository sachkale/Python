pipeline {
  agent any
  stages{
  
  
  stage('SCM') 
    {
      steps{
    checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'sachkale', url: 'https://github.com/sachkale/Python.git']]])
   sh 'ls -lrt'
        
      }
  }
    
  stage('SonarQube Analysis') 
    steps{
    {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
}
}
