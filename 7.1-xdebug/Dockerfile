FROM kevindierkx/php-ci:7.1
MAINTAINER Kevin Dierkx <kevin@pcextreme.nl>

# Setup configs
COPY config/xdebug.ini $PHP_INI_DIR/conf.d/

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

RUN echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini \
 && echo "xdebug.remote_enable=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
 && echo "xdebug.remote_autostart=off" >> /usr/local/etc/php/conf.d/xdebug.ini

CMD ["php", "-a"]
