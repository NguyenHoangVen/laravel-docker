FROM php:8.2-fpm

# Install PHP extensions
RUN apt-get update && apt-get install -y \
    zip unzip libzip-dev libpng-dev \
    && docker-php-ext-install zip pdo pdo_mysql

# Install Composer from official image
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www