FROM kevindierkx/php-ci:7.1
MAINTAINER Kevin Dierkx <kevin@pcextreme.nl>

# Install xdebug
RUN docker-php-source extract \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
    && docker-php-source delete

# Copy configuration
COPY xdebug.ini /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini

CMD ["php", "-a"]