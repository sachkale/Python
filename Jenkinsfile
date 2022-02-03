node {
  stage('SCM') {
    git branch: 'main', credentialsId: 'sachkale', url: 'https://github.com/sachkale/Python.git'
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
