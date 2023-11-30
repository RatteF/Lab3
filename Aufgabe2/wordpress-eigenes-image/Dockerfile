# Verwenden Sie Debian als Basisimage
FROM debian:bullseye-slim

# Aktualisieren Sie die Paketliste und installieren Sie notwendige Pakete
RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends apache2 php php-cli php-mysql \
    && rm -rf /var/lib/apt/lists/*

# Apache-Module aktivieren
RUN a2enmod rewrite

# Konfigurationen kopieren
COPY apache2.conf /etc/apache2/apache2.conf
COPY 000-default.conf /etc/apache2/sites-available/000-default.conf

# WordPress-Installation (Anpassungen können erforderlich sein)
COPY wordpress/ /var/www/html/

# Persistente Volumes für hochgeladene Dateien und Konfiguration
VOLUME /var/www/html/wp-content

# Exponieren Sie den Port 80
EXPOSE 80

# Apache im Vordergrund ausführen
CMD ["apache2", "-D", "FOREGROUND"]