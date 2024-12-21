pipeline {
  /*
   * TODO: Implement pipeline stages/steps
   *   See documentation: https://www.jenkins.io/doc/book/pipeline/syntax/#stages
   */
  stages {
    stage('Build') {
      steps {
        sh './gradlew assemble'
      }
    }
    stage('Test') {
      steps {
        sh './gradlew test'
      }
    }
  }
}
post {
  always {
    archiveArtifacts artifacts: '**/build/libs/*.jar', allowEmptyArchive: true
    junit 'build/test-results/test/*.xml'
  }
}
