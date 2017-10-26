FROM node:6
MAINTAINER Perry Tsai
WORKDIR /var/web
COPY ["server.js", "entrypoint.sh", "package.json", "./"]
RUN npm install
ENTRYPOINT ["sh","entrypoint.sh"]
EXPOSE 8080
