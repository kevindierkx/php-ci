FROM php:5.6-cli
MAINTAINER Kevin Dierkx <kevin@pcextreme.nl>

# Install additional
RUN apt-get update && apt-get install -y \
        libmcrypt-dev \
        git \
    && docker-php-ext-install \
        mbstring \
        mcrypt \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

CMD ["php", "-a"]
