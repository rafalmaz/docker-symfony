FROM php:7.4-fpm

COPY docker/php/php.ini /usr/local/etc/php/conf.d/docker-php-config.ini

RUN apt-get update && apt-get -y --no-install-recommends \
        install \
        ssh \
        libaio-dev \
        build-essential \
        unzip \
        git \
        unzip \
        zlib1g-dev \
        libxml2-dev \
        libzip-dev \
        libpq-dev \
    && docker-php-ext-install \
        zip \
        intl \
        pgsql \
        pdo pdo_pgsql


RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/symfony