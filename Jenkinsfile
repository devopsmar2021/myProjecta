pipeline {
  agent { label 'slave1' }
  tools {
    maven 'maven381'
  }
  stages {
    stage('checkout') {
      steps {
        git 'git@github.com:devopsmar2021/myProjecta.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
