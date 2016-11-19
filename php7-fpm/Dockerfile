FROM alpinelib/s6:latest
MAINTAINER Maxime FRANCK

RUN apk add --no-cache --repository http://nl.alpinelinux.org/alpine/edge/testing \
  --repository http://nl.alpinelinux.org/alpine/edge/main \
  --repository http://nl.alpinelinux.org/alpine/edge/community \
  php7-apcu	php7-bz2 php7-curl php7-dba php7-dev php7-exif php7-fpm php7-gd php7-iconv php7-imap php7-intl \
  php7-json php7-ldap php7-mcrypt php7-openssl php7-pdo_mysql php7-pdo_pgsql php7-pear php7-pspell php7-shmop \
  php7-snmp php7-soap php7-sockets php7-sqlite3 php7-sysvmsg php7-sysvsem php7-sysvshm php7-xml php7-xmlreader \
  php7-xmlrpc php7-zip php7-zlib php7-ssh2 php7-phar \
  acl bzip2 gzip imagemagick openssl \
  mysql-client sqlite sqlite-dev ssmtp


RUN php7 -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php7 -r "if (hash_file('SHA384', 'composer-setup.php') === 'aa96f26c2b67226a324c27919f1eb05f21c248b987e6195cad9690d5c1ff713d53020a02ac8c217dbf90a7eacc9d141d') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" \
    && php7 composer-setup.php \
    && php7 -r "unlink('composer-setup.php');"


ADD root /

EXPOSE 9000
