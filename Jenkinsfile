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
          }
      }
     
     
     stage('Code Checkout') {
          steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'GITHUB_credentials', url: 'https://github.com/sachkale/Python.git']]])
          }
      }
     
     stage('CodeQuality') {
          steps {
                 withSonarQubeEnv('My SonarQube Server', envOnly: true) {
                  // This expands the evironment variables SONAR_CONFIG_NAME, SONAR_HOST_URL, SONAR_AUTH_TOKEN that can be used by any script.
                  echo '${env.SONAR_HOST_URL}' 
          }
          }
      }
       
   }
}
