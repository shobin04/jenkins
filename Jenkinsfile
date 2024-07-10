pipeline {
    agent any
    
    stages {
        stage ('SCM checkout') {
           steps {
               git 'https://github.com/shobin04/jenkins.git'
            }
        }   
        stage ('build') {
            steps {
               sh""" cd /var/lib/jenkins/workspace/Demo-Project/java-maven-app-master/
               mvn package
               """
            }
        }  
        stage ('deploy') {
            steps {
                 sh""" sudo cp /var/lib/jenkins/workspace/Demo-Project/java-maven-app-master/target/my-app-1.0-SNAPSHOT.war /opt/tomcat/webapps
                 sudo systemctl restart tomcat
                 """
            }
        }   
        stage('SonarQube Analysis') {
            def scannerHome = tool 'SonarQube Scanner';
            withSonarQubeEnv() {
               sh "${scannerHome}/opt/sonar-scanner"
           }
        }
    }
}
