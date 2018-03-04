FROM php:7.2-fpm

RUN apt-get update && apt-get -y install redis-tools

RUN pecl install redis

RUN curl -sS https://getcomposer.org/installer | php \
        && mv composer.phar /usr/local/bin/composer

RUN bash -c "echo extension=redis.so > /usr/local/etc/php/conf.d/redis.ini"

RUN bash -c "echo session.save_handler = \"redis\" >> /usr/local/etc/php/conf.d/redis.ini"
RUN bash -c "echo session.save_path = \"tcp://redis:6379\" >> /usr/local/etc/php/conf.d/redis.ini"

CMD ["php-fpm"]