FROM alpine
MAINTAINER Perry Tsai<ripple0129@gmail.com>
RUN apk update && apk add nginx \
    && apk add openrc --no-cache \
    && adduser -D -u 1000 -g 'www' www \
    && mkdir /www \
    && chown -R www:www /var/lib/nginx \
    && chown -R www:www /www \
    && rm -rf /var/cache/apk/*
COPY nginx.conf /etc/nginx/nginx.conf
ENTRYPOINT ["rc-service","nginx","start"]
