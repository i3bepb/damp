FROM php:7.4-apache

RUN apt-get update && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libmcrypt-dev sendmail libpng-dev zlib1g-dev libxml2-dev libzip-dev libonig-dev graphviz \
    && docker-php-ext-install mysqli pdo pdo_mysql zip iconv mbstring && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd && docker-php-source delete && pecl install mcrypt-1.0.3 && a2enmod rewrite
# RUN service apache2 restart

CMD ["apachectl", "-D", "FOREGROUND"]