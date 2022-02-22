node {
  stage('SCM') {
    git 'https://github.com/busraktan/NetCoreDeneme.git'
  }
  stage('SonarQube analysis') {
    def scannerHome = tool 'SonarScanner 5.4';
    withSonarQubeEnv('My SonarQube Server') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
