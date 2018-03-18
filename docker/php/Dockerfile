FROM php:7.2-fpm


RUN apt-get update && apt-get -y install wget redis-tools

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
    && docker-php-ext-install -j$(nproc) iconv zip pdo_mysql \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

RUN pecl install redis

RUN curl -sS https://getcomposer.org/installer | php \
        && mv composer.phar /usr/local/bin/composer

RUN bash -c "echo extension=redis.so > /usr/local/etc/php/conf.d/redis.ini"

RUN bash -c "echo session.save_handler = \"redis\" >> /usr/local/etc/php/conf.d/redis.ini"
RUN bash -c "echo session.save_path = \"tcp://redis:6379\" >> /usr/local/etc/php/conf.d/redis.ini"

CMD ["php-fpm"]