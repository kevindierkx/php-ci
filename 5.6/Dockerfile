FROM php:5.6-alpine
MAINTAINER Kevin Dierkx <kevin@pcextreme.nl>

# Install libraries
RUN apk add --no-cache --virtual .persistent-deps \
        icu-dev \
        libmcrypt-dev \
        openssh-client \
        git

# Install PHP extensions
RUN apk add --no-cache --virtual .build-deps \
        autoconf \
        g++ \
    && docker-php-ext-configure intl \
    && docker-php-ext-install intl \
    && docker-php-ext-install mcrypt \
    && apk del .build-deps

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

CMD ["php", "-a"]
