FROM kevindierkx/php-ci:7.1
MAINTAINER Kevin Dierkx <kevin@pcextreme.nl>

# Install xdebug
RUN apk add --no-cache --virtual .build-deps \
        autoconf \
        g++ \
        make \
    && docker-php-source extract \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
    && docker-php-source delete \
    && apk del .build-deps

# Copy configuration
COPY xdebug.ini /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini

CMD ["php", "-a"]
