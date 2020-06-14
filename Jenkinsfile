pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = $M2_HOME/bin:$PATH"
                    echo "M2_HOME = /opt/maven3"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true install' 
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}
