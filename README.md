# Docker Drupal Image

[![Build Status](https://travis-ci.org/jrobinsonc/docker-drupal-image.svg?branch=master)](https://travis-ci.org/jrobinsonc/docker-drupal-image)

<https://hub.docker.com/r/jrobinsonc/drupal/>

## Includes

* [PHP extensions](https://www.drupal.org/docs/8/system-requirements/php-requirements#extensions) required by Drupal.
* [Composer](https://getcomposer.org/)
* [Drupal Console](https://drupalconsole.com/)

**Image Variants**

* PHP 7.3 with Apache → `jrobinsonc/drupal:7.3-apache`
* PHP 7.2 with Apache → `jrobinsonc/drupal:7.2-apache`

## How to use

**Start the container:**

```shell
docker run -d \
  -p 80:80 \
  -p 443:443 \
  -v $(pwd):/var/www/html \
  jrobinsonc/drupal:7.3-apache
```
