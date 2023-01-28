# Java Spring Cloud demo 

[![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)

All credits for https://github.com/ronniemikihiro creator,
this project is a fork from https://github.com/ronniemikihiro/microservices-spring-cloud

project to make a scratch of use cases for Spring cloud 

This repository contains:
- simple demo shows how works spring cloud eureka discovery and gateway 

This project uses
- maven
- java jdk17
- spring cloud 
- docker
# website 
find more edvelopment info at my website https://qleoz12.github.io/

## Arquitecture 

![Alt text](./docs/arquitectura.drawio.png?raw=true "Arquitecture microservices")

## Install

set the variable `DIRECTORY_HOME` inside the bat mvn_clean_package_DOCKER.bat where you clone the project
after that run the .bat

```sh
$ mvn_clean_package_DOCKER.bat
```
when all projects build correctly you could run up the docker-compose
```sh
$ devops/docker-compose up -d 
```
check the logs an  validate the conection with the next section

## Usage
### CREATE TOKEN
- URL DIRECT: http://localhost:8080/auth/token
- URL CLOUD GATEWAY: http://localhost:8080/auth/token
- Body: x-www-form-urlencoded / username: admin / password: teste

### REFRESH TOKEN
- URL DIRECT: http://localhost:8080/auth/refreshToken
- URL CLOUD GATEWAY: http://localhost:8080/auth/refreshToken
- Body: x-www-form-urlencoded / refresh_token: (refresh_token gerado no CREATE TOKEN)

### CONSULT USER
- URL DIRECT: http://localhost:8082/api-user/***
- URL CLOUD GATEWAY: http://localhost:8080/api-user/***
- Authorization: Bearer Token / Token: (acces_token gerado no CREATE TOKEN OU REFRESH TOKEN)

### CONSULT USER-DATA
- URL DIRECT: http://localhost:8083/api-user-data/***
- URL GATEWAY ZUUL: http://localhost:8080/api-user-data/***
- Authorization: Bearer Token / Token: (acces_token gerado no CREATE TOKEN OU REFRESH TOKEN)

### DISCOVERY
URL SPRING EUREKA: http://localhost:8081/discovery

### references
- https://github.com/ronniemikihiro/microservices-spring-cloud
- https://github.com/PacktPublishing/Mastering-Microservices-with-Java-9-Second-Edition (Chapter 06)
- https://www.amazon.com/Mastering-Microservices-Java-domain-driven-microservice-based/dp/1787281442?
- https://github.com/serlesen/microservices-bookstore
- https://www.youtube.com/watch?v=iwq0rc-PYNQ&list=PLab_if3UBk9-BjDP7Yh4uiy8z0pEd14Tp
