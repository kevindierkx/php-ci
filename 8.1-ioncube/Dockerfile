FROM kevindierkx/php-ci:8.1

LABEL maintainer="Kevin Dierkx <kevin@distortedfusion.com>"

# Install IonCube Loader
ADD https://downloads.ioncube.com/loader_downloads/ioncube_loaders_lin_x86-64.tar.gz /tmp/

RUN tar -C /tmp -xzvf /tmp/ioncube_loaders_lin_x86-64.tar.gz \
    && mkdir -p /usr/local/ioncube && cp /tmp/ioncube/*.so /usr/local/ioncube \
    && rm /tmp/ioncube_loaders_lin_x86-64.tar.gz && rm -rf /tmp/ioncube

COPY config/00-ioncube.ini $PHP_INI_DIR/conf.d/

CMD ["php", "-a"]
