#  DevOps Practice exercise 1

- Jenkins Installation
    ```
    Install Jenkins using Docker method
    Install Jenkins on a Linux machine (RedHat/Centos/Amazon Linux)
    Install Jenkins on Linux using Web application Archive (WAR) file
    ```
<br>

- Create a new GitLab repository and upload the script [bash.sh](/bash.sh) to it. Then configure a new Jenkins job to pull the code from your repository and run the script
<br>

- Create a new Slack channel (use your own workspace) and sent the notification post the above build to the channel
<br>

- Setup a Jenkins build Pipeline with Build, Test, Package, and Deploy using the following code base. Ensure to fork the codebase to your gitlab account and to the pipeline creation
<br>

    **https://gitlab.cloudifyops.com/clops-training/java-maven-app.git**

<br>

- Following are the stages expected from the above codebase
    ```
    1) Git checkout
    2) Compile (mvn compile)
    3) Build (mvn -B -DskipTests clean package
    4) Test (mvn test)
    5) Upload the artifact build to Nexus repository (install on the same box) 
    6) Deploy to tomcat running on a remote machine 
    ```
<br>

- Integrate the Sonar scanning into the above pipeline
<br>

- Configure the Webhook to ensure it is continuous integration via the pipeline
<br>

- Send the success/failure notification your cloudifyops email id and slack channel you created previously
<br>

- Add a Linux Node  to the Jenkins and assign to the above job to the slave machine
<br>

- Checkout the maximum number of jobs that we can run concurrently on Jenkins. Set the maximum value to "3”
<br>

- How to reset the build number in Jenkins for the above job?
<br>

- Schedule the above job to run nightly daily at 9 pm
<br>

- Execute Shell Script after post build of the above job in Jenkins 
<br>

<div align="Right">
    <img src="images/Cloudifyops-Logo.jpg" alt="Logo" width="100" height="40">
</div>

# DevOps Excercise - 2

## Fork repo 

1) Fork [this](https://gitlab.cloudifyops.com/clops-devops-learning-nd-training/petclinic_non-microservice) repo to your Cloudifyops gitlab account.
2) If you do not have a Cloudifyops Gitlab login, please reachout to Kumar/Vipin/Vyshnav
3) Follow the [best practices](https://gitlab.cloudifyops.com/clops-gitlab/clops-gitlab-best-practices) always

## Install & Configure Jenkins

1) Create a EC2 instance on your Free Tier AWS Account and install Jenkins
2) Install necessary Jenkins Plugins
3) Install GIT and Maven manually on the Jenkins EC2 machine and manually configure the path in the Jenkins settings (Global Tools)
4) Ensure jenkins will be started up during reboots


## Install & Configure SonarQube

1) Create a EC2 instance on your Free Tier AWS Account and install SonarQube
2) Install SonarQube scanner on Jenkins EC2 instnace. Configure Jenkins to connect with the sonarqube
3) Enable startup script for sonarqube
4) [Reference](https://www.devopshint.com/how-to-install-sonarqube-on-amazon-linux-2/)
5) [Reference](https://community.sonarsource.com/t/running-sonarqube-as-a-service-on-linux-documentation-centos-7/2941)
 
## Install & Configure PetClinic Application

Spin up a new EC2 instnace and perform the following

1) Install latest version of [Tomcat](https://tomcat.apache.org/). 
2) Clone the [PetClinic Application](https://gitlab.cloudifyops.com/clops-training/devops-practice-exercise-2.git) to your local machine and perform a local mvn build on your machine
3) Deploy the Petclinic Application war/ear file to Tomcat manually and test the working.

## Install & Configure Ansible

1) Install [Ansible](https://www.ansible.com/) and configure Ansible plugin on Jenkins
2) Create a Ansible role to deploy the petclinic war on the tomcat. Push this code your gitlab repo. 

## Create a Jenkins pipeline

Create a Jenkins file your petclinic repo with the below stages for your automated CICD pipeline.

<div align="center">
    <img src="images/DevOps-Excercise-1.png" alt="DevOps-Excercise-1">
</div>

```
1) Git Checkout :: PetClinic Repo
2) Git Checkout :: Ansbile Repo
3) Unit test
4) SonarQube Analysis
5) QualityGate Check
6) Build Stage
7) Deploy :: Using Ansible
8) Secuirty Test
9) Performance Testing
```


  * First and Second stages should run parallel
  * Deploy the application war file after the build using ansible to tomcat 
  * For stage 8 - Use [Zap Proxy ](https://www.zaproxy.org/). You can use zap.sh for the same.
  * For stage 9 - use [Jmeter](https://jmeter.apache.org/). You can use petclinic_test_plan.jmx script for the same
  * Configure webhook trigger to automate the CICD pipeline for each commit
  * [Reference](https://www.jenkins.io/doc/book/pipeline/syntax/)
  * [Reference](https://www.lambdatest.com/blog/jenkins-declarative-pipeline-examples/)
 
 


#### Spring PetClinic Sample Application

This repo is a fork of the [spring-projects/spring-petclinic](https://github.com/spring-projects/spring-petclinic).

It allows the Spring community to maintain a Petclinic version with a plain old ****Spring Framework configuration**** and with a ****3-layer architecture****.

##### Understanding the Spring Petclinic application with a few diagrams

[See the presentation here](http://fr.slideshare.net/AntoineRey/spring-framework-petclinic-sample-application) (2017 update)



