FROM php:7.4-fpm

RUN docker-php-ext-install mysqli
 
# Para instalar la extension GD
COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/

RUN install-php-extensions gd

EXPOSE 9000