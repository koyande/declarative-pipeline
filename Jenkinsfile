pipeline {
    def mvn = tool (name: 'maven3', type: 'maven') + '/bin/mvn'
    stages {
        stage ('Build') {
            steps {
                sh "${mvn} -Dmaven.test.failure.ignore=true install"
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}
