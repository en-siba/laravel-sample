FROM php:7-fpm

ENV WWW_ROOT /var/www
ENV PUBLIC_ROOT /var/www/public

RUN apt-get update && apt-get install -y \
   vim \
   zip \
   unzip \
   iputils-ping \
   git
RUN docker-php-ext-install pdo_mysql
RUN git clone https://github.com/en-siba/laravel-sample.git /var/www/public
RUN cd /var/www/public && \
   chmod -R 777 storage/ && \
   chmod -R 777 bootstrap/cache && \
   curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer && \
   composer install && \
   cp .env.example .env && \
   php artisan key:generate

