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
          expression { BRANCH_NAME ==~ /master/ }
          environment name: 'CHANGE_ID', value: null
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