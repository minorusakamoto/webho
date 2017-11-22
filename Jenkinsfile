pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Version') {
          agent {
            label 'master'
          }
          steps {
            sh './gradlew -v'
          }
        }
        stage('echo') {
          agent {
            label 'master'
          }
          steps {
            echo 'ECHO'
          }
        }
        stage('ENV') {
          agent {
            label 'master'
          }
          steps {
            sh 'env'
          }
        }
        stage('ls') {
          agent {
            label 'master'
          }
          steps {
            sh 'ls -l'
          }
        }
      }
    }
  }
  options {
    timestamps()
  }
}