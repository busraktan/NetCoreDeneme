node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def msbuildHome = tool 'MSBuild'
    def scannerHome = tool 'sonarqube'
    withSonarQubeEnv() {
      sh "\"${scannerHome}\\SonarScanner.MSBuild.exe\" begin /k:\"Deneme\""
      sh "\"${msbuildHome}\\MSBuild.exe\" /t:Rebuild"
      sh "\"${scannerHome}\\SonarScanner.MSBuild.exe\" end"
    }
  }
}
