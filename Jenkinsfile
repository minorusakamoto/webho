pipeline {
    agent any

    stage('Build') {
        parallel master:{
            node('master'){
                steps {
                    sh './gradlew tasks'
                }
            }
        },
        master2:{
            node('master'){
                steps {
                    sh './gradlew -v'
                }
            }
        }
    }
}