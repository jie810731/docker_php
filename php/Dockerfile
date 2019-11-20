FROM php:7.2-fpm

RUN apt-get update \
    && apt-get install -y \
        libzip-dev \
        zip \
        libpng-dev \
    && docker-php-ext-install pdo_mysql\
    && pecl install -o -f redis \
    && docker-php-ext-enable redis \
    && docker-php-ext-configure zip --with-libzip \
    && docker-php-ext-install zip \
    && docker-php-ext-install gd

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
#RUN curl --silent --show-error https://getcomposer.org/installer | php