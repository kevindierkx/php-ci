FROM php:5.6
MAINTAINER Kevin Dierkx <kevin@distortedfusion.com>

# Setup configs
COPY config/memory.ini $PHP_INI_DIR/conf.d/

# Install libraries
RUN apt-get update && apt-get install -y \
        autoconf \
        g++ \
        git \
        libicu-dev \
        libmcrypt-dev \
        netbase \
        openssh-client

# Install PHP extensions
RUN docker-php-ext-configure intl \
    && docker-php-ext-install intl \
    && docker-php-ext-install mcrypt

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

CMD ["php", "-a"]
