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

