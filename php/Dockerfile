FROM php:7.0-fpm
RUN apt-get update && apt-get install -y libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
    && pecl install redis-3.1.3 \
    && docker-php-ext-enable redis  \
    && docker-php-ext-configure gd --with-png-dir --with-freetype-dir --with-jpeg-dir --with-gd \
    && docker-php-ext-install gd mysqli pdo_mysql zip opcache
ADD composer.phar /usr/local/bin/composer
RUN chmod 755 /usr/local/bin/composer
