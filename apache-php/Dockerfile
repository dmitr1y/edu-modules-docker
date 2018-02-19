FROM ubuntu:16.04

RUN apt-get update && \
        apt-get -y install software-properties-common \
        xvfb \
        locales && \
        locale-gen en_US.UTF-8 && \
        export LC_ALL=en_US.UTF-8 && \
        export LANG=en_US.UTF-8 && \
        add-apt-repository ppa:ondrej/php && \
        apt-get update && \
        DEBIAN_FRONTEND=noninteractive apt-get -y --allow-unauthenticated install \
        apache2 \
        php7.1 \
        php7.1-dev \
        php7.1-curl \
        php7.1-cli \
        php7.1-gd \
        php7.1-bcmath \
        php7.1-json \
        php7.1-ldap \
        php7.1-intl \
        php7.1-mbstring \
        php7.1-mcrypt \
        php7.1-mysql \
        php7.1-xml \
        php7.1-xsl \
        php7.1-zip \
        php7.1-soap \
        libapache2-mod-php7.1 \
        git \
        curl &&\
        apt-get clean && \
        rm -rf /var/lib/apt/lists/*

RUN a2enmod rewrite
ADD shell.conf /etc/apache2/sites-enabled/000-default.conf

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/bin
RUN mv /bin/composer.phar /bin/composer

RUN composer global require "fxp/composer-asset-plugin"
CMD cd /srv/www/edu && composer install --no-interaction && apachectl -D FOREGROUND