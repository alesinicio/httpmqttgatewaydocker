FROM phpdockerio/php73-fpm:latest

# Fix debconf warnings upon build
ARG DEBIAN_FRONTEND=noninteractive

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install php7.3-dev php-pear libmosquitto-dev build-essential \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# INSTALL mosquitto-php
RUN pecl install Mosquitto-alpha

# REMOVE
RUN apt remove build-essential; apt auto-remove -y
