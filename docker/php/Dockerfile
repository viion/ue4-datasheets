FROM php:7.4-fpm

#
# Update
#
RUN apt-get update && apt-get upgrade -y && rm -rf m -rf /var/lib/apt/lists/*

#
# Extensions
#
RUN docker-php-ext-install mysqli pdo pdo_mysql && rm -rf /tmp/*

#
# Composer
#
RUN rm -rf /var/cache/apk/* && rm -rf /tmp/* && \
    curl --insecure https://getcomposer.org/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer

#
# Copy config
#
ADD config.ini $PHP_INI_DIR/conf.d/

#
# Fin
#
WORKDIR /var/www/project
EXPOSE 9000

CMD ["php-fpm"]
