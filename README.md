# Docker & DataDog

The goal of our project is to monitor the docker-engine, but also the container of it.
To reach this, we are using Datadog, wich allows to monitor a lot of details of the docker-engine, but also every images that are installed, the consumption of those and since how long they are up.
This project is a school research for dockers, so it is not optimal and can be upgraded with many features.

## Install

To install and use our project it's necessary to create an account on :
https://app.datadoghq.eu/signup 

Be careful on the region used, it may be a problem if you don't choose the correcte one. And get the API key after creating the account.

It's necessary to create an account here to pull the images : https://hub.docker.com/

The next step consist of pulling all the images, in order to manage them with Datadog. To do this step, you have to pull them with :

- docker pull jwagneritescia/docker:DDIMG
- docker pull jwagneritescia/docker:nginx
- docker pull jwagneritescia/docker:jenkins

Once the images are pulled, you can start them with : 

- DOCKER_CONTENT_TRUST=1 docker run --name Datadog -p 8125:80 -d jwagneritescia/docker:DDIMG
- DOCKER_CONTENT_TRUST=1 docker run -d -v /var/run/docker.sock:/var/run/docker.sock:ro -v /proc/:/host/proc/:ro -v /sys/fs/cgroup/:/host/sys/fs/cgroup:ro -e DD_API_KEY="YOURAPIKEY" datadog/agent:latest
- docker run --name Nginx -p 8080:80 -d jwagneritescia/docker:nginx
- docker run --name Jenkins -p 5000:80 -d jwagneritescia/docker:jenkins

To show the status of current active images, use the command : 
- docker images

To show the ID and the port, this command can be helpful : 
- docker ps -a

## How to use

Once the images are pulled and started, type into the web browser the address :

https://app.datadoghq.eu/

Every images are automatically up into Datadog, just as informations about the docker-engine. 

To see informations about the docker engine go to "Dashboard -> Dashboard list -> docker engine"

For informations about containers go to "Infrastructure -> Containers"

Datadog can be modified as much as the user wants. Don't be afraid to create new dashboard and explore them with the different options !

With portainers, it is possible to reboot, stop, create, export, tag and import containers. To access to this, go to the web browser : 
- "IPADDRESS:9000"

As it is a graphic mode, it's much more easier to use.


## Versions

To this project, we decided to use the following versions : 
- Datadog agent : 7.0
- Nginx : 1.18.0-alpine
- Portainers : 1.24
- Jenkins : 2.60.3

## Default ports

- Datadog : 8125
- Nginx : 8080
- Portainers : 9000
- Jenkins : 5000

## Links

 - https://hub.docker.com/repository/docker/jwagneritescia/docker
 - https://github.com/JordanWagnerRES/Docker
 - https://app.datadoghq.eu/signup

## Importants point

If you planned to use this project, please be careful on :

- The version of the containers installed
- The port-mapping of the differents images (locally and on docker-hub)
- The environment variable on each Dockerfile
- Don't forget to paste your API key of Datadog when starting the containers

## Collaborators

Florian C. - Yasmine B. A. - Jordan W.
