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
    stage('env') {
      when {
        expression {
           ${CHANGE_ID} != null &&　${CHANGE_ID} != ""
        }
      }
      steps {
        sh "echo ${env.CHANGE_ID}"
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