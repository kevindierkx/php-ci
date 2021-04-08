FROM php:7.4.16
MAINTAINER Kevin Dierkx <kevin@distortedfusion.com>

# Setup configs
COPY config/memory.ini $PHP_INI_DIR/conf.d/

# Install libraries
RUN apt-get update && apt-get install -y \
        alien \
        autoconf \
        fakeroot \
        g++ \
        git \
        libicu-dev \
        netbase \
        openssh-client \
        unzip \
        libzip-dev

# Install PHP extensions
RUN docker-php-ext-configure intl \
    && docker-php-ext-install intl \
    && docker-php-ext-install zip

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

CMD ["php", "-a"]
