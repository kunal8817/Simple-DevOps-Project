
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

# What is Docker Hub Registry ??
Docker Hub is a cloud-based registry service which allows you to link to code repositories, build your images and test them, stores manually pushed images, and links to Docker Cloud so you can deploy images to your hosts. It provides a centralized resource for container image discovery, distribution and change management, user and team collaboration, and workflow automation throughout the development pipeline.

Ref URL : https://docs.docker.com/docker-hub/

1.) Create a docker hub account in https://hub.docker.com/

2.) Pull a docker image.
```sh
docker pull ubuntu
```

3.) Pull a docker image with the old version
```
docker pull ubuntu:16.04
```
4.) create a custom tag to the docker image
```
docker tag ubuntu:latest kunal8817/ubuntu:demo
```
5.) login to your docker hub registry
```
docker login --> Provide the dockerhub login details
docker push kunal8817/ubuntu:demo
```

#### Testing
1.) Remove all images in docker server
```
docker rmi <IMAGE ID>
```
2.) Pull your custom image from your docker account
```
docker pull kunal8817/ubuntu:demo
```

