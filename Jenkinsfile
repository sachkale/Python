pipeline {
  agent any
  
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
     
      stage ('Initialize') {
        steps {
                
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
               
            }
        }

        stage ('Build') {
            steps {
                mvn -Dmaven.test.failure.ignore=true install
            }
      }
       
   }
   }
