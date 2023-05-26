FROM php:8.0-cli

LABEL maintainer="Kevin Dierkx <kevin@distortedfusion.com>"

# Setup configs
COPY config/memory.ini $PHP_INI_DIR/conf.d/

# Install libraries
RUN apt-get update \
    && apt-get install -y \
        alien \
        autoconf \
        fakeroot \
        g++ \
        git \
        libicu-dev \
        libxml2-dev \
        libzip-dev \
        netbase \
        openssh-client \
        rpm \
        rsync \
        unzip

# Install PHP extensions
RUN docker-php-ext-configure intl \
    && docker-php-ext-install bcmath \
    && docker-php-ext-install soap \
    && docker-php-ext-install xml \
    && docker-php-ext-install intl \
    && docker-php-ext-install zip

RUN apt-get -y autoremove \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

CMD ["php", "-a"]
