FROM php:7.2-fpm


RUN curl -sS https://getcomposer.org/installer | php \
        && mv composer.phar /usr/local/bin/composer


CMD ["php-fpm"]