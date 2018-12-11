FROM php:7.3-fpm

RUN apt-get update -y \
    && apt-get install curl

RUN curl --insecure https://getcomposer.org/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer

ADD symfony.ini /etc/php7/conf.d/
ADD symfony.ini /etc/php7/cli/conf.d/
ADD xdebug.ini  /etc/php7/conf.d/

RUN apt-get install -y \
        libzip-dev \
        zip \
  && docker-php-ext-configure zip --with-libzip \
  && docker-php-ext-install zip

WORKDIR /var/www/symfony
EXPOSE 9001