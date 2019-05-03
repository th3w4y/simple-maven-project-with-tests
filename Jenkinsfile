pipeline { 
    agent {
        kubernetes {
          //cloud 'kubernetes'
          label 'mypod'
          containerTemplate {
            name 'maven'
            image 'maven:3.3.9-jdk-8-alpine'
            ttyEnabled true
            command 'cat'
          }
        }
    stages {
        stage ('Build') {
            steps {
                    sh 'mvn -Dmaven.test.failure.ignore=true package'

            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml'
                }
            }
        }
        
        stage ('Deploy to Test environment') {
            steps {
                sh 'echo Deploy to Test environment TBD'
            }
        }
    }
}
