[![Docker Pulls](https://img.shields.io/docker/pulls/michaelpporter/jenkins-php.svg)](https://hub.docker.com/r/michaelpporter/jenkins-php)
[![Docker Stars](https://img.shields.io/docker/stars/michaelpporter/jenkins-php.svg)](https://hub.docker.com/r/michaelpporter/jenkins-php)
[![Docker Layers](https://images.microbadger.com/badges/image/michaelpporter/jenkins-php.svg)](https://microbadger.com/images/michaelpporter/jenkins-php)

# Jenkins PHP

PHP 7 testing based on the official Jenkins Docker image [jenkins/jenkins:lts](https://hub.docker.com/r/jenkins/jenkins/)

This is a Durpal/php test suite for building jobs in Jenkins.

## Included tools

- pdepend
- phpcpd
- phpcs
    + Drupal coder
    + `phpcs --standard=Drupal --extensions='php,module,inc,install,test,profile'`
    + Wordpress Coding Standards
    + `phpcs --standard=Wordpress --extensions='php,module,inc,install,test,profile'`
- phploc
- phpmd
- phpunit

## docker-compose.yml

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

## Docker4Drupal

A sample setup using [docker4drupal](https://github.com/wodby/docker4drupal) included.
