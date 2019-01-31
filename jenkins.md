# JENKINS AND GITHUB WEBHOOK
# Jenkins
> Jenkins is an open source automation server intended to automate repetitive technical tasks involved in the continuous integration and delivery of software. Jenkins is Java-based and can be installed from Ubuntu packages or by downloading and running its Web application ARchive (WAR) file — a collection of files that make up a complete web application which is intended to be run on a server.In this tutorial we will install Jenkins by adding its Debian package repository, then using that repository to install the package using apt-get.
>
> [Click here to get Jenkins Installed](https://www.digitalocean.com/community/tutorials/how-to-install-jenkins-on-ubuntu-16-04)
>
[Ensure that java *jre* and *jdk* files are installed before installing *jenkins*](https://www.linode.com/docs/development/java/install-java-on-ubuntu-16-04/)
> 
# Creating a job(new item)
* Select freestyle project when creating a new item and then click OK
* *General* - In the next Window,Select the *Github project* checkbox
![GENERAL](https://github.com/GitanjaliRavichandran/git/blob/master/Selection_005.png)
* *Source Code Management* - Select the *Git* radio button and give the repository URL
![Source Code Management](https://github.com/GitanjaliRavichandran/git/blob/master/Selection_006.png)

* *Build* - Click on EXecute Shell and type the following code inorder to automate the Build trigger
* *Build Triggers* - Select the GitHub hook trigger for GITScm polling checkbox
>
# Shell script
```
#!/bin/sh
ssh gitanjali@192.168.1.127
echo "Script executed from: ${PWD}"
p="/var/www/html/" 
cd "$p" 
echo "Script executed after: ${PWD}"
git clone https://github.com/GitanjaliRavichandran/git.git
p1="git"
cd "$p1"
git pull origin master
echo "ok"

```
While executing the above script,Set the permissions for the users,groups and others respectively inorder to execute the script efficiently.
>

# Github Webhook
* Choose *Settings* in the repository you are working
* Select *Webhooks* in the left pane
* Click on *Add Webhook* and give the payload url
* *Payload Url* - The payload URL is the URL of the server that will receive the webhook ```POST``` requests.
```
http://ip address:8080/github-webhook/  
```
* *Content Type* - Webhooks can be delivered using different content types:
  1. The ```application/json``` content type will deliver the JSON payload directly as the body of the POST request
  2. The ```application/x-www-form-urlencoded``` content type will send the JSON payload as a form parameter called payload
* *Active* - By default, webhook deliveries are "Active." You can choose to disable the delivery of webhook payloads by deselecting "Active
* Finally Click on Add Webhooks


# Reference
* [https://developer.github.com/webhooks/creating/](https://developer.github.com/webhooks/creating/)
* [https://thepracticalsysadmin.com/setting-up-a-github-webhook-in-jenkins/](https://thepracticalsysadmin.com/setting-up-a-github-webhook-in-jenkins/)
* [https://www.youtube.com/watch?v=Z3S2gMBUkBo](https://www.youtube.com/watch?v=Z3S2gMBUkBo)
