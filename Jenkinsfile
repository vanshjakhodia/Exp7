pipeline {
    agent any
    tools {
        maven 'Maven3'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker cp target/Exp7.war tomcat_container:/usr/local/tomcat/webapps/ROOT.war'
                sh 'docker restart tomcat_container'
            }
        }
    }
}

