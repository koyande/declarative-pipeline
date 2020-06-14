pipeline {
    agent any
  
    stages {
        stage ('Build') {
            steps {
                sh '${mvn} clean package deploy'
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml'
                }
            }
        }
    }
}
