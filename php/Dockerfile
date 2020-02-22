FROM php:7.2-fpm

ENV DEBCONF_NOWARNINGS yes

# For composer
RUN apt-get update \
    && apt-get install -y libzip-dev zlib1g-dev \
    && docker-php-ext-install zip

# Install composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php \
    && php -r "unlink('composer-setup.php');" \
    && mv composer.phar /usr/local/bin/composer

# Set composer environment
ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_HOME /composer
ENV PATH $PATH:/composer/vendor/bin

# Install laravel installer
RUN composer global require "laravel/installer"

# PHP's DB setting
RUN apt-get update \
    && apt-get install -y libpq-dev libfreetype6-dev libjpeg62-turbo-dev libpng-dev libjpeg-dev
RUN docker-php-ext-configure gd --with-png-dir=/usr/include --with-jpeg-dir=/usr/include
RUN docker-php-ext-install gd pdo_mysql pdo_pgsql

# Install Node.js
RUN apt-get install -y gnupg
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs

WORKDIR /src
