FROM nimmis/alpine-micro
MAINTAINER Perry Tsai<ripple0129@gmail.com>
RUN apk update && apk add lighttpd\
    php5-common \
    php5-iconv \
    php5-json \
    php5-gd \
    php5-curl \
    php5-xml \
    php5-pgsql \
    php5-imap \
    php5-cgi \
    fcgi \
    php5-pdo \
    php5-pdo_pgsql \
    php5-soap \
    php5-xmlrpc \
    php5-posix \
    php5-mcrypt \
    php5-gettext \
    php5-ldap \
    php5-ctype \
    php5-dom \
    && rm -rf /var/cache/apk/*
RUN apk update && apk add php5-mysql php5-mysqli
RUN mkdir /etc/service/lighttpd \
    && mkdir /run/lighttpd \
    && chmod -R 777 /run
COPY run /etc/service/lighttpd/
RUN chmod +x /etc/service/lighttpd/run
COPY lighttpd.conf /etc/lighttpd/lighttpd.conf
COPY mod_fastcgi.conf /etc/lighttpd/mod_fastcgi.conf
WORKDIR /usr/share/webapps
ADD phpMyAdmin-4.5.0.2-all-languages.tar.gz /usr/share/webapps
RUN mv phpMyAdmin-4.5.0.2-all-languages phpmyadmin \
    && chmod -R 777 /usr/share/webapps/ \
    && ln -s /usr/share/webapps/phpmyadmin/ /var/www/localhost/htdocs
