node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') 
  {
    def scannerHome = tool 'sonarqube'
    withSonarQubeEnv() {
      sh "dotnet ${scannerHome}/SonarScanner.MSBuild.dll begin /k:\"Deneme\""
      sh "dotnet build"
      sh "dotnet ${scannerHome}/SonarScanner.MSBuild.dll end"
    }
    
  }
}
