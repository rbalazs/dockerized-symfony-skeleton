FROM php:7.1.3-fpm

WORKDIR /app

RUN apt-get update && apt-get install -y apt-utils vim curl net-tools dialog zip bash git && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN docker-php-ext-install pdo pdo_mysql

RUN pecl install xdebug
RUN docker-php-ext-enable xdebug

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN usermod -u 1000 www-data

RUN mkdir -p /run/php/ && chown -R www-data:www-data /run/php/

EXPOSE 9000