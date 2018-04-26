FROM php:7.1-fpm
#basics
RUN apt-get update && apt-get install -y imagemagick zip unzip wget nano curl git mysql-client libtidy-dev libpng12-dev libjpeg-dev libicu52 libicu-dev g++ libmagickwand-6.q16-dev && rm -rf /var/lib/apt/lists/* \

# create symlink to support standard /usr/bin/php
&& ln -s /usr/local/bin/php /usr/bin/php \

#composer (global)
&& curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \

# gd
&& docker-php-ext-configure gd --with-jpeg-dir=/usr/lib && docker-php-ext-install gd \

#mysql
&& docker-php-ext-install mysqli \

#mbstring
&& docker-php-ext-install mbstring \

#html tidy
&& docker-php-ext-install tidy \

# Install opcache
&& docker-php-ext-install opcache \

#APCU
&& pecl install apcu \
&& echo "extension=apcu.so" > /usr/local/etc/php/conf.d/apcu.ini \

#intl
&& docker-php-ext-install intl \

#imagick
&& ln -s /usr/lib/x86_64-linux-gnu/ImageMagick-6.8.9/bin-Q16/MagickWand-config /usr/bin/ && pecl install imagick && echo "extension=imagick.so" > /usr/local/etc/php/conf.d/ext-imagick.ini \

#socket extension
&& docker-php-ext-install sockets \
