node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv('sonarqube-server') {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=zivcohenoz_jenkins_4fd6fb4a-cee0-43b6-95de-ba3f039c44b9 -Dsonar.projectName='jenkins'"
    }
  }
}