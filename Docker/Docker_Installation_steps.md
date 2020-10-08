# Dillinger

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

# Installing Docker on Amazon Linux server !

##### Pre-Requisite:
- Amazon Linux EC2 Instance

##### Installation Steps
1.) Install docker and start docker services.
```sh
yum install docker -y
docker --version 

# start docker services
service docker start
service docker status
```

2.) Create a user called dockeradmin
```
useradd dockeradmin
passwd dockeradmin
```
3.) add a user to docker group to manage docker
```
usermod -aG docker dockeradmin
```
#### Validation test
1.) Create a tomcat docker container by pulling a docker image from the public docker registry
```
docker run -d --name test-tomcat-server -p 8090:8080 tomcat:latest
```

### Docker Installation on CentOS server

Referance URL : https://docs.docker.com/install/linux/docker-ce/centos/#install-using-the-repository

##### Pre-Requisite:
Please follow below steps to install docker CE on CentoOS server instance. For RedHat only Docker EE available

1.) Install the required packages.
```
sudo yum install -y yum-utils \
device-mapper-persistent-data \
lvm2
```
2.) Use the following command to set up the stable repository.
```
sudo yum-config-manager \
--add-repo \
https://download.docker.com/linux/centos/docker-ce.repo
```
##### INSTALLING DOCKER CE
1.) Install the latest version of Docker CE.
```
sudo yum install docker-ce
```
> Note: If prompted to accept the GPG key, verify that the fingerprint matches 060A 61C5 1B55 8A7F 742B 77AA C52F EB6B 621E 9F35, and if so, accept it.

2.) Start Docker.
```
sudo systemctl start docker
```
3.) Verify that docker is installed correctly by running the hello-world image.
```
sudo docker run hello-world
```
