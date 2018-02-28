pipeline {
  agent {
    node {
      label 'master'
    }
  }
  stages {
    stage('Version') {
      steps {
        sh './gradlew -v'
        sh 'env'
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