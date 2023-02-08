FROM php:8.2-cli-alpine3.17

# Install system dependencies
RUN apk add --no-cache zip unzip curl supervisor

# Installing bash
RUN apk add bash
RUN sed -i 's/bin\/ash/bin\/bash/g' /etc/passwd

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

# Install PHP extensions
RUN install-php-extensions \
    bcmath \
    csv \
    exif \
    gd \
    geospatial \
    gettext \
    grpc \
    intl \
    ldap \
    mongodb \
    mysqli \
    opcache \
    pdo_mysql \
    pdo_pgsql \
    pgsql \
    redis \
    sockets \
    swoole \
    zip \
    xdebug \
    @composer
