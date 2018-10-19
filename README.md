# spring-cloud-docker-sample
Example of running Spring Application with Eureka and Config servers in Docker.

This is how to setup and run example.

NOTE: Make sure you have Docker and Maven installed.

Build the example with Maven:
> mvn compile jib:dockerBuild

This will create 3 separate docker images:
* spring-cloud-docker-eureka-server
* spring-cloud-docker-config-server
* spring-cloud-docker-app

Initialize Git config repository (use by Config server):
> cd git_config

> git init

> cd ..

Run using docker-compose:
> docker-compose up

The end result is this:
* When application boots, it will register itself with the Eureka server. After that, it will lookup Config server and fetch all of its configuration. At last it will print the **spring.data.mongodb.uri** property to System.out.
