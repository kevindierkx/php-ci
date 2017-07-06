FROM php:7.1-alpine
MAINTAINER Kevin Dierkx <kevin@pcextreme.nl>

RUN echo '@community http://nl.alpinelinux.org/alpine/edge/community' >> /etc/apk/repositories

# Install libraries
RUN apk add --no-cache --virtual .persistent-deps \
        icu-dev \
        openssh-client \
        git

# Install PHP extensions
RUN apk add --no-cache --virtual .build-deps \
        autoconf \
        g++ \
    && docker-php-ext-configure intl \
    && docker-php-ext-install intl \
    && apk del .build-deps

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install PHP deps
RUN apk add --update \
    php7-xdebug@community

CMD ["php", "-a"]