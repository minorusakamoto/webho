pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                label 'master'
            }
            steps {
                echo 'Build'
            }

        }
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
