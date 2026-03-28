# https://hub.docker.com/_/php
FROM php:8.5.4-fpm

ENV TZ=Asia/Tokyo

RUN apt update

# Composer システム要件
# https://getcomposer.org/doc/00-intro.md#system-requirements
RUN apt install -y libzip-dev zip unzip
RUN docker-php-ext-configure zip
RUN docker-php-ext-install zip

# Laravel システム要件
# https://laravel.com/docs/13.x/deployment#server-requirements
# 今の Docker イメージですべて有効化されている

# PostgreSQL の場合
RUN apt install -y libpq-dev
RUN docker-php-ext-install pdo_pgsql

RUN apt clean
RUN rm -rf /var/lib/apt/lists/*

WORKDIR /src
