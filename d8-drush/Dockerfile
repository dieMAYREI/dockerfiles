FROM diemayrei/d8-php-apache

RUN apt-get update && apt-get install -y --no-upgrade mysql-client \
    && rm -rf /var/lib/apt/lists/*

RUN curl -L -o drush.phar https://github.com/drush-ops/drush-launcher/releases/download/0.6.0/drush.phar \
  && chmod +x drush.phar \
  && mv drush.phar /usr/local/bin/drush

WORKDIR /var/www/html

ENTRYPOINT ["/usr/local/bin/drush"]
