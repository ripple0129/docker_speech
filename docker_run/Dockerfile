FROM alpine
MAINTAINER Perry Tsai
RUN apk update && apk upgrade \
    && apk add nodejs \
    && apk add nodejs-npm \
    && rm -rf /var/cache/apk/*
WORKDIR /app
COPY ["package.json", "server.js", "/app/"]
RUN npm install
ENTRYPOINT [ "npm", "start" ]
