
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

# Install and configure Maven build tool on Jenkins
Maven is a code build tool which is used to convert your code into an artifact. This is a widely used plugin to build in continuous integration.

### Pre-Requisites

- Jenkins Server

### Install Maven on Jenkins

1.) Download maven packages [https://maven.apache.org/download.cgi][PlDb] onto Jenkins server. In this case I am using /opt/maven as my installation directory.

```sh
#Creating maven directory under /opt
$ mkdir /opt/maven
$ cd /opt/maven
# downloading maven version 3.6.0
$ wget http://mirrors.estointernet.in/apache/maven/maven-3/3.6.1/binaries/apache-maven-3,6,1-bin.tar.gz
$ tar -xvzf apache-maven-3,6,1-bin.tar.gz
```
2.) Setup M2_HOME and M2 paths in .bash_profile of the user and add these to path variable

```sh
$ vi ~/.bash_profile
$ M2_HOME=/opt/maven/apache-maven-3,6,1
$ M2=$M2_HOME/bin
$ PATH=<EXISTING_PATH>:$M2_HOME:$M2
```

### Chekpoint
1.) Logoff and login again to check the maven version
```
mvn --version
```
So far we have completed the installation of maven software to support maven plugin on the jenkins console. Let's jump into the Jenkins to complete the remaining steps.

### Setup Maven on Jenkins Console

1.) Install Maven plugin without restart.
- Manage Jenkins > Jenkins Plugins > Available > Maven Invoker
- Manage Jenkins > Jenkins Plugins > Available > Maven Integration

2.) Configure Maven path.

- Manage Jenkins > Global Tool Configuration > Maven

