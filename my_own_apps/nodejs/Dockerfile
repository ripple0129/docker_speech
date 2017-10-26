FROM alpine
MAINTAINER Perry Tsai<ripple0129@gmail.com>
WORKDIR /var/web
COPY ["server.js", "entrypoint.sh", "package.json", "./"]
RUN apk update \
    && apk add nodejs \
    && apk add nodejs-npm \
    && npm install \
    && rm -rf /var/cache/apk/*
ENTRYPOINT ["sh","entrypoint.sh"]
EXPOSE 8080
