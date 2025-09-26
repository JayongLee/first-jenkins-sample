node {
  stage('SCM') {
    checkout scm
    sh 'chmod +x gradlew'     // ★ 반드시 추가
  }
  stage('SonarQube Analysis') {
    withSonarQubeEnv() {
      sh "./gradlew sonar"
    }
  }
}