FROM php:7.2-apache

RUN a2enmod rewrite headers

RUN apt-get update && apt-get install -y --no-upgrade \
    zlib1g-dev \
    libicu-dev \
    libxslt-dev \
    libxml2 \
    locales \
    && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install -j$(nproc) pdo_mysql iconv mbstring mysqli zip intl xml xsl \
	&& docker-php-source delete

RUN sed -i -e 's/# de_DE.UTF-8 UTF-8/de_DE.UTF-8 UTF-8/' /etc/locale.gen && locale-gen
