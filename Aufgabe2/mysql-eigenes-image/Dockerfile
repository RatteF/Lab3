FROM debian:bullseye

WORKDIR /app

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        gnupg2 \
        dirmngr \
        wget \
        lsb-release \
        ca-certificates \
    && echo "deb http://repo.mysql.com/apt/debian/ $(lsb_release -sc) mysql-8.0" > /etc/apt/sources.list.d/mysql.list \
    && wget -O /tmp/RPM-GPG-KEY-mysql https://repo.mysql.com/RPM-GPG-KEY-mysql \
    && apt-key --keyring /usr/share/keyrings/mysql-archive-keyring.gpg add /tmp/RPM-GPG-KEY-mysql \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        mysql-server \
    && rm -rf /var/lib/apt/lists/*

EXPOSE 3306

CMD ["mysqld"]
