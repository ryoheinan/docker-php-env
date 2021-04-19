FROM php:7.4-apache
SHELL ["/bin/bash", "-oeux", "pipefail", "-c"]

RUN apt-get update && \
  apt-get -y install git unzip libzip-dev libicu-dev libonig-dev vim && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/* && \
  docker-php-ext-install intl pdo_mysql zip bcmath

COPY ./php.ini /usr/local/etc/php/php.ini
COPY ./apache/*.conf /etc/apache2/sites-enabled/

RUN  a2enmod rewrite

WORKDIR /var/www/html
