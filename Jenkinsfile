pipeline {
    agent any
    stages {
        stage('Build') {
            parallel {
                stage('Tasks') {
                    agent {
                        label 'master'
                    }
                    steps {
                        sh './gradlew tasks'
                    }
                }
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
    }
}
