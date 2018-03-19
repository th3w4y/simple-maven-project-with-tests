pipeline { 
    agent {
        label 'maven-jdk-8'
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
