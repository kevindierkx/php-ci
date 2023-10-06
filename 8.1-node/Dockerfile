FROM node:latest AS node
FROM kevindierkx/php-ci:8.1

LABEL maintainer="Kevin Dierkx <kevin@distortedfusion.com>"

COPY --from=node /usr/local/lib/node_modules /usr/local/lib/node_modules
COPY --from=node /usr/local/bin/node /usr/local/bin/node
RUN ln -s /usr/local/lib/node_modules/npm/bin/npm-cli.js /usr/local/bin/npm

CMD ["php", "-a"]
