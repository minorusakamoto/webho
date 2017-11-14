node('master') {
    stages {
        stage('Build') {
            parallel master:{
                steps {
                    sh './gradlew tasks'
                }
            },
            master2:{
                steps {
                    sh './gradlew -v'
                }
            }
        }
    }
}