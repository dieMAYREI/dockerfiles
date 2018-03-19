FROM php:7.1-apache

RUN a2enmod rewrite \
	&& apt-get update && apt-get upgrade -y \
	libfreetype6-dev \
	libjpeg62-turbo-dev \
	libpq-dev \
	libmagickwand-dev \
	libmcrypt-dev \
	libpng12-dev \
	libmemcached-dev \
	libssl-dev \
	libssl-doc \
	libsasl2-dev \
	zlib1g-dev \
	libicu-dev \
	g++ \
	&& rm -rf /var/lib/apt/lists/* \
	&& docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
	&& docker-php-ext-install -j$(nproc) pdo_mysql bz2 iconv mbstring mcrypt mysqli soap zip gd intl \
	&& pecl install imagick && docker-php-ext-enable imagick \
	&& pecl install redis-3.1.1 && docker-php-ext-enable redis \
	&& docker-php-source delete

RUN apt-get update && apt-get install -y ssmtp && rm -rf /var/lib/apt/lists/*
