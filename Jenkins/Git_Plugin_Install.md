
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

# Configure Git plugin on Jenkins
Git is one of the most popular tools for version control system. You can pull code from git repositories using jenkins if you use github plugin.

### Pre-Requisites

- Jenkins Server

##### Install Git on Jenkins server

```sh
$ yum install git -y
```
##### Setup Git on Jenkins Console

1.) Install Git plugin without restart.
- Manage Jenkins > Jenkins Plugins > Available > Github

2.) Configure Git path.
- Manage Jenkins > Global Tool Configuration > git

