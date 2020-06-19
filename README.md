# Docker & DataDog

The goal of our project is to monitor the docker-engine, but also the container of it.
To reach this, we are using Datadog, wich allows to monitor a lot of details of the docker-engine, but also every images that are installed, the consumption of those and since how long they are up.
This project is a school research for dockers, so it is not optimal and can be upgraded with many features.

## How to use it

## Versions

To this project, we decided to use the following versions : 
- Datadog : 7.0
- Nginx : 1.18.0 - alpine
- Portainers : 1.24
- Jenkins : 2.60.3

## Default ports

- Datadog : 8125
- Nginx : 8080
- Portainers : 9000
- Jenkins : 5000

## Importants point

If you planned to use this project, please be careful on :

- The version of the containers installed
- The port-mapping of the differents images (locally and on docker-hub)
- The environment variable on each Dockerfile

## Collaborators

Florian C. - Yasmine B. A. - Jordan W.
