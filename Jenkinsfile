node {
  stage('SCM') {
    checkout scm
    sh 'chmod +x gradlew'     // ★ 반드시 추가
  }

  stage('Build') {
    sh './gradlew clean build -x test'  // 빌드 먼저 실행
  }

  stage('SonarQube Analysis') {
    withSonarQubeEnv() {
     sh './gradlew sonarqube --no-daemon'
    }
  }
}