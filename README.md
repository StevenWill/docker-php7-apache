# docker-PHP-7-apache
Build a Drupal environment with docker containers for apache, mysql, solr and redis.

This repository contains a custom image from the php:7-apache docker image.
If you do not already have this docker image built it will build on your
first docker-compose up

Next you can start your stack with the docker-compose command
> docker-compose up

If you do not already have a mysql and html folder they will be created.
You can now add the Drupal code base to the html/docroot folder.

Configure your settings file with MySQL, and Redis.
Mysql will use the host as "db" and the database and
user info defined in the docker-compose file.
Redis uses port 6375

SSH into your apache container by listing the containers
> docker ps

Use the container id to execute bash in the container
> docker exec -it YOUR_DOCKER_NAME /bin/bash

Importing db from outside the container
> docker exec -i CONTAINERNAME mysql -u root -pmysql wordpress < ./backup.sql

