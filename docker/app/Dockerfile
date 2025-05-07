FROM php:8.4-fpm

ENV TZ=Asia/Tokyo

RUN apt-get update && \
    apt-get install -y git unzip libzip-dev libicu-dev libonig-dev \
                       libpq-dev && docker-php-ext-install intl pdo_mysql zip bcmath pdo_pgsql

COPY ./docker/app/php.ini /usr/local/etc/php/php.ini

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /app