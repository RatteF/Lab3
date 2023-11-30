FROM debian:bullseye-slim

RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends apache2 php php-cli php-mysql \
    && rm -rf /var/lib/apt/lists/*

RUN a2enmod rewrite

VOLUME /var/www/html/wp-content

EXPOSE 80

CMD ["apache2", "-D", "FOREGROUND"]
