# Dillinger

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Dillinger is a cloud-enabled, mobile-ready, offline-storage, AngularJS powered HTML5 Markdown editor.

  - Type some Markdown on the left
  - See HTML in the right
  - Magic

# Install Jenkins on AWS EC2 Instance
Jenkins is a self-contained Java-based program, ready to run out of the box, with pacakages for Windows, Mac OS X and other Unix-like operating systems. As anextensible automation sever, Jenkins can be used as a simple CI server or turned into the continuos delivery hub for any project.


### Pre-Requisites

- EC2 Instace with port 8080 opened in Security Group for internet.
- Java v1.8x

### Install Java

1.) We will be using open java for our demo, get the latest version from [http://openjdk.java.net/install][PlDb]

```sh
$ yum install java-1.8*
#yum -y install java-1.8.0-openjdk-devel
```
2.) Confirm Java version and set the java home

```sh
$ java -version
$ find /usr/lib/jvm/java-1.8* | head -n 3
$ JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-<JAVA Version which is seen in the above output>
$ export JAVA_HOME
$ PATH=$PATH:$JAVA_HOME
## To set it permanently update your .bash_profile
$ vi ~/.bash_profile
```

The output will be something like this 
```
java version "1.8.0_261"
Java(TM) SE Runtime Environment (build 1.8.0_261-b12)
Java HotSpot(TM) 64-Bit Server VM (build 25.261-b12, mixed mode)
```

### Install Jenkins

You can install jenkins using the rpm or setting up the repo. We will set up the repo so that we can update it easily in future.

1.) Getthe latest version of jenkins from [https://pkg.jenkins.io/redhat-stable/][PlDb] and install.
   ```
      yum -y install wget
      sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins
      sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
      yum -y install jenkins
      
```
   ### Start Jenkins
   
   #Start the Jenkins Servie
   
    $ service jenkins start
    
   #Setup Jenkins to start at boot
   
    $ chkconfig jenkins on 
    
### Accessing Jenkins
By Default jenkins runs at port 8080 , so you can access jenkins at

>http://YOUR-SERVER-PUBLIC-IP:8080

### Configure Jenkins
- The Default Username is "admin"
- Grab the password from the location [/var/lib/jenkins/secret/initialAdminPassword]
- Skip the Plugin Installation.
- Change Admin password.
          Admin > Configure > Password
- Configure Java path.
          Manage Jenkins > Global Tool Configuration > JDK
- Create another admin user ID.
 
### Test jenkins Jobs
- Create "new item"
- Enter an Item name -- My-First-Project
- Choose Freestyle project
- Under the build section execute shell :- echo "Welcome to Jenkins Demo"
- Save your job
- Build Job
- Check "console output"


