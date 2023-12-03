# JCasC
JCasC stands for Jenkins Configuration as Code, in this project we will use JCasC plugin to make a preconfigured Jenkins instance running as a Docker container.
## Description
This project aims to create and configure a kubernetes cluster on the cloud from scratch (the same principle can be applied in an on-premises infrastructure without needing a kubernetes service), so in this project you'll learn how to manage kubernetes components and understand more about kubernetes architecture and tools.

## Project components and files + detailed description
**Dockerfile:** this Dockerfile describes the custom Jenkins image we'll be working on.

**plugins.txt:** In this file, you'll list the plugins you want. These plugins will be installed as soon as the custom Jenkins image is created.

**casc.yaml:** this file contains the Jenkins configuration as code used by the JCasC plugin to perform the desired initial configurations.

**pipeline.groovy:** this file contains your Jenkins pipelines for provisioning.

**docker-compose.yml:** this docker compose file is used to launch the jenkins container instance with the correct parameters (such as volumes and environment variables).

**.env:** this file contains the environment variables used by the jcasc plugin.

## Visuals
**Architecture:**

![architecture](./READMEimages/jcasc-architecture.png)

## Usage
**Step 1:**

- clone the repository on your local machine.

**Step 2:**

- change the variables in the .env file.
- modify the plugins in plugins.txt to install the plugins you want, but *do not delete the configuration-as-code plugin* as it is used to perform configurations.
- modify the pipeline.groovy by adding your pipelines.

**Step 3:**

- create the custom image.
  inside the root directory of this project run:
```shell
$ docker build -t jenkins:jcasc .
```

**Step 4:**

- run the created Jenkins image. 
```shell
$ docker-compose up -d 
```

## Support

- for help contact me on my email address : tbn.khalil@gmail.com 

## Project status

**active**
