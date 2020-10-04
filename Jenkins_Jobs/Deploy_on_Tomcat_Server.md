# Dillinger

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

# Deploy on a Tomcat server !

## Jenkins Job name: Deploy_on_Tomcat_Server

##### Pre-Requisite:
- Jenkins Server
- Tomcat Server

##### Adding Deployment steps
1.) Install 'deploy to container' plugin. This plugin needs to deploy on tomcat server.
* Install 'deploy to container' plugin without restart
  - Manage Jenkins > Jenkins Plugins > available > deploy to container

2.) Jenkins should need access to the tomcat server to deploy build artifacts. setup credentials to enable this process. use credentials option on Jenkins home page.
> setup credentials 
```sh
- credentials > jenkins > Global credentials > add credentials
- Username : deployer
- Password : deployer
- id : deployer
- Description: user to deploy on tomcat vm
```

#### Steps to create "Deploy_on_Tomcat_Server" Jenkin job
1.) From Jenkins home page select "New Item"
* Enter an item name: Deploy_on_Tomcat_Server
  - Copy from: My_First_Maven_Build

2.) Source Code Management:
* Source Code Management:
  - Repository: https://github.com/kunal8817/hello-world.git
  - Branches to build : */master
* Build:
  - Root POM: pom.xml
  - Goals and options: clean install package
 
* Poll SCM : - * * * *
* Post-build Actions : 
Deploy war/ear to container
WAR/EAR files : **/*.war
Containers : Tomcat 8.x
Credentials: deployer (user created on above)
Tomcat URL : http://<PUBLIC_IP>:8080

3.) Save and run the job now.

