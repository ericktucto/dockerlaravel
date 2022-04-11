FROM php:7.4-fpm
LABEL "Author: Erick Tucto"
LABEL "Email: erick.tucto@outlook.com"
LABEL "Github: https://github.com/ErickTucto"
LABEL "Website: https://ericktucto.com"

USER $USER

RUN apt-get update \
    && apt-get install -y libjpeg62-turbo-dev \
        libpng-dev \
        libzip-dev \
        gnupg2 \
        git \
        unzip \
        zip \
    && apt-get clean \
    && rm -Rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
    && docker-php-ext-configure bcmath --enable-bcmath \
    && docker-php-ext-configure gd --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-configure pdo \
    && docker-php-ext-configure pdo_mysql --with-pdo-mysql=mysqlnd \
    && docker-php-ext-install pdo_mysql bcmath zip mysqli \
    && mkdir /run/php \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

