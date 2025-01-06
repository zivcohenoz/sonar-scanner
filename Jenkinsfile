node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube analysis') {
    tools {
        jdk "jdk17" // the name you have given the JDK installation in Global Tool Configuration
    }
    environment {
        scannerHome = tool 'sonar-scanner' // the name you have given the Sonar Scanner (in Global Tool Configuration)
    }
    steps {
        withSonarQubeEnv(installationName: 'sonarqube-server') {
            sh "${scannerHome}/bin/sonar-scanner -X"
        }
    }
}
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
      echo "RUNNING: sh ${scannerHome}/bin/sonar-scanner"
    }
  }
}