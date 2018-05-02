pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }

  }
  stages {
    stage('Build') {
      steps {
        git(branch: 'master', url: 'https://github.com/lbrandis/TestingBlueOcean', credentialsId: 'Git')
        sh 'mvn clean install -DskipTests'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }
    stage('Deliver') {
      steps {
        sh '''chmod 777 ./jenkins/scripts/deliver.sh
./jenkins/scripts/deliver.sh'''
      }
    }
  }
}