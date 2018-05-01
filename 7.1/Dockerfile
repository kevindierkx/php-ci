FROM php:7.1-alpine
MAINTAINER Kevin Dierkx <kevin@pcextreme.nl>

# Install libraries
RUN apk add --no-cache --virtual .persistent-deps \
        icu-dev \
        openssh-client \
        git \
        libxml2-dev

# Install PHP extensions
RUN apk add --no-cache --virtual .build-deps \
        autoconf \
        g++ \
    && docker-php-ext-configure intl \
    && docker-php-ext-install intl soap \
    && apk del .build-deps

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

CMD ["php", "-a"]
