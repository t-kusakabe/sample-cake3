FROM php:7.3.10-fpm-alpine3.10

ADD composer.json composer.lock ./
COPY docker/php/php.ini /usr/local/etc/php/

WORKDIR /sample-cake-dusk-app

RUN cd /usr/bin && curl -s http://getcomposer.org/installer | php && ln -s /usr/bin/composer.phar /usr/bin/composer && \
  apk add --no-cache \
    zlib-dev \
    libzip-dev \
    icu-dev && \
  docker-php-ext-install \
    pdo_mysql \
    zip \
    intl

# CMD ['composer', 'install']
