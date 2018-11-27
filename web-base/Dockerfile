FROM php:7.1-apache

RUN a2enmod rewrite

RUN apt-get update && apt-get install -y --no-upgrade \
    zlib1g-dev \
    libicu-dev \
    && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install -j$(nproc) pdo_mysql iconv mbstring mysqli zip intl \
	&& docker-php-source delete

RUN apt-get update && apt-get install -y --no-upgrade \
    locales \
    && rm -rf /var/lib/apt/lists/*

RUN sed -i -e 's/# de_DE.UTF-8 UTF-8/de_DE.UTF-8 UTF-8/' /etc/locale.gen && locale-gen
