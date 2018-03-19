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
        
        stage ('Notify') {
            steps {
              sh 'echo "Notify Slack/HipChat/etc/..."'
            }
        }

    }
}
