FROM php:7.2-fpm

RUN apt-get update \
    && docker-php-ext-install pdo_mysql\
    && pecl install -o -f redis \
    &&  docker-php-ext-enable redis