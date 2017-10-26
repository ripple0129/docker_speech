FROM alpine
MAINTAINER Perry Tsai
RUN apk update \
    && apk add --update mysql \
    && rm -rf /var/cache/apk/*
WORKDIR /app
ENV MYSQL_ROOT_PASSWORD=123123123
COPY my.cnf /etc/mysql/my.cnf
COPY entrypoint.sh /app/
ENTRYPOINT ["sh","entrypoint.sh"]
