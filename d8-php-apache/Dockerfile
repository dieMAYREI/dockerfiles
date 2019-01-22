FROM diemayrei/web-base

RUN apt-get update && apt-get install -y --no-upgrade \
    libjpeg-dev \
	libfreetype6-dev \
	libjpeg62-turbo-dev \
	libpq-dev \
	libmagickwand-dev \
	libmemcached-dev \
	libssl-dev \
	libssl-doc \
	libsasl2-dev \
	libjpeg-turbo-progs \
	jpegoptim optipng \
	&& rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
	&& docker-php-ext-install -j$(nproc) gd \
	&& pecl install imagick && docker-php-ext-enable imagick \
	&& pecl install redis-4.1.1 && docker-php-ext-enable redis \
	&& docker-php-source delete

COPY jfifremove /usr/local/bin/jfifremove
