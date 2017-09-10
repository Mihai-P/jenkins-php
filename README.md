# Jenkins PHP

PHP 7 testing based on [jenkins/jenkins:lts](https://hub.docker.com/r/jenkins/jenkins/)

This is a Durpal/php test suite for building jobs in Jenkins.

## Included tools

- pdepend
- phpcpd
- phpcs
- phploc
- phpmd
- phpunit

## docker-compose

```
version: "2"

services:
  jenkins:
    image: xenomedia/jenkins-php:latest
    ports:
      - 8080:8080
      - 50000:50000
    volumes:
      - ./jenkins_home:/var/jenkins_home
      - ./path/to/drupal:/var/www/html # Docker-sync
#    labels:
#      - 'traefik.backend=jenkins_jenkins_1'
#      - 'traefik.port=8888'
#      - 'traefik.frontend.rule=Host:jenkins.drupal.docker.localhost'
```
