pipeline {
    agent any
    
    stages {
        stage ('SCM checkout') {
           steps {
               git 'https://github.com/shobin04/jenkins.git'
            }
        }   
    stage('SonarCloud') {
          environment {
            SONAR_RUNNER_HOME = tool 'SonarQube Scanner'
            PROJECT_NAME = "sample"
          }
          steps {
            withSonarQubeEnv('SonarCloudOne') {
                sh '''cd /var/lib/jenkins/workspace/java-maven-project/java-maven-app-master \
                mvn clean verify sonar:sonar \
               -Dsonar.projectKey=sample \
               -Dsonar.projectName='sample' \
               -Dsonar.host.url=http://54.227.43.162:9000 \
               -Dsonar.token=sqp_f864753e09846383d7dffce1302d4376944d454d
              '''
             }
          }
       }
        stage ('build') {
            steps {
               sh""" cd /var/lib/jenkins/workspace/java-maven-project/java-maven-app-master/
               mvn package
               """
            }
        }  
        stage ('deploy') {
            steps {
                 sh""" sudo cp /var/lib/jenkins/workspace/java-maven-project/java-maven-app-master/target/my-app-1.0-SNAPSHOT.war /opt/tomcat/webapps
                 sudo systemctl restart tomcat
                 """
            }
        }   
    }
}
