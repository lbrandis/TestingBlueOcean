pipeline {
  agent any
  stages {
    stage('Build') {
      agent {
        docker {
          image 'maven:3-alpine'
          args '-v /root/.m2:/root/.m2'
        }

      }
      steps {
        git(branch: 'master', url: 'https://github.com/lbrandis/TestingBlueOcean', credentialsId: 'Git')
        sh 'mvn clean install -DskipTests'
      }
    }
  }
}