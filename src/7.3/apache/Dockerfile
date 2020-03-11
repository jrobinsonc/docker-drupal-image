# Based on
# https://www.drupal.org/docs/8/system-requirements/web-server
# https://www.drupal.org/docs/8/system-requirements/php-requirements

FROM jrobinsonc/php:7.3-apache

RUN set -ex; \
    apt-get update; \
    apt-get install -y --no-install-recommends \
      mariadb-client \
      libfreetype6-dev \
      libjpeg-dev \
      libmagickwand-dev \
      libpng-dev \
    ; \
    pecl install imagick-3.4.4; \
    rm -rf /var/lib/apt/lists/*;

RUN set -eux; \
    docker-php-ext-configure gd --with-freetype-dir=/usr --with-jpeg-dir=/usr --with-png-dir=/usr; \
    docker-php-ext-install -j "$(nproc)" \
      gd \
      pdo_mysql \
      opcache \
    ; \
	  docker-php-ext-enable \
      imagick \
    ;

# Install Drupal Console
RUN curl https://drupalconsole.com/installer -L -o drupal.phar; \
  mv drupal.phar /usr/local/bin/drupal; \
  chmod +x /usr/local/bin/drupal; \
  drupal self-update

RUN a2enmod rewrite expires headers
