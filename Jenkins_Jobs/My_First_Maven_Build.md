# Dillinger

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

# Create a First Maven Jenkins job to build hello-world project !

## Jenkins Job name: My_First_Maven_Build
We know how to use work with both git and Jenkins independently. What if you want to collaborate these two? that is where Simple DevOps project helps you. Follow the below steps if you are a new to DevOps.

##### Pre-Requisite:
- Jenkins Server

#### Steps to create "My_First_Maven_Build" Jenkin job
1.) Login to Jenkins console
2.) Create Jenkins job, Fill the following details.
* Source Code Management:
  - Repository: https://github.com/yankils/hello-world.git
  - Branches to build : */master
* Build:
  - Root POM: pom.xml
  - Goals and options: clean install package

