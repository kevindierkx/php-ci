FROM php:5.6-alpine
MAINTAINER Kevin Dierkx <kevin@pcextreme.nl>

# Install PHP extensions
RUN apk update \
    && apk add --no-cache --virtual .phpize-deps \
        libmcrypt-dev \
    && docker-php-ext-install \
        mcrypt

# Install GIT
RUN apk add --no-cache --virtual .persistent-deps \
        openssh-client \
        git

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

CMD ["php", "-a"]
