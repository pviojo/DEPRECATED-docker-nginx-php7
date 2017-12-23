FROM php:7.1-fpm
MAINTAINER Pablo Viojo <pviojo@gmail.com>

######
# You can install php extensions using docker-php-ext-install
######

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libcurl3-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
        git \
        vim \
        libxml2-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt pdo_mysql mysqli curl zip \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

# Install phpredis extension
ENV PHPREDIS_VERSION 3.1.5

RUN mkdir -p /usr/src/php/ext/redis \
    && curl -L https://github.com/phpredis/phpredis/archive/$PHPREDIS_VERSION.tar.gz | tar xvz -C /usr/src/php/ext/redis --strip 1 \
    && echo 'redis' >> /usr/src/php-available-exts \
    && docker-php-ext-install redis

# Composer
RUN curl -s https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer

ENV PATH="$PATH:/root/.composer/vendor/bin"
