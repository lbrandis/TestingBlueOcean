pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        build 'mvn -B clean install'
      }
    }
  }
}