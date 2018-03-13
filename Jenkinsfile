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
    stage('Build') {
      when {
        allOf {
          expression { currentBuild.result == null || currentBuild.result == 'SUCCESS' }
          allOf {
            environment name: 'CHANGE_ID', value: null
            expression { BRANCH_NAME == 'master' }
          }
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