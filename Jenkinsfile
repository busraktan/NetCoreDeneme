node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') 
  {
    def scannerHome = tool 'sonarqube'
    withSonarQubeEnv() {
      sh "dotnet ${scannerHome}/SonarScanner.MSBuild.dll begin /k:\"Deneme-projesi\""
      sh "dotnet build"
      sh "dotnet ${scannerHome}/SonarScanner.MSBuild.dll end"
      sonar.login=admin
      sonar.password=Punish2o21!+
    }
    
  }
}
