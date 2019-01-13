FROM php:7.2-apache
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -yq --no-install-recommends \
	libpng-dev \
    apt-utils \
    curl 
RUN apt-get update && apt-get install -y libpng-dev 
RUN apt-get install -y \
    libwebp-dev \
    libjpeg62-turbo-dev \
    libpng-dev libxpm-dev \
    libxml2-dev libxslt-dev\
    libfreetype6-dev

RUN docker-php-ext-configure gd \
    --with-gd \
    --with-webp-dir \
    --with-jpeg-dir \
    --with-png-dir \
    --with-zlib-dir \
    --with-xpm-dir \
    --with-freetype-dir \
    --enable-gd-native-ttf

RUN docker-php-ext-install gd

RUN docker-php-ext-install \
    pdo_mysql \
    && a2enmod \
    rewrite
RUN docker-php-ext-install mbstring

RUN docker-php-ext-install zip

RUN docker-php-ext-install bcmath

RUN docker-php-ext-install soap

RUN docker-php-ext-install xsl

RUN docker-php-ext-install intl

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# RUN a2enmod rewrite expires
RUN service apache2 restart

WORKDIR /var/www/html/



