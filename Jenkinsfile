pipeline {
  agent {
    node {
      label 'master'
    }
  }
  stages {
    stage('Build') {
      stage('Version') {
        agent {
          label 'master'
        }
        steps {
          sh './gradlew -v'
        }
      }
    }
  }
  environment {
    JAVA_HOME = '/opt/java/jdk1.8'
  }
  options {
    timestamps()
  }
}