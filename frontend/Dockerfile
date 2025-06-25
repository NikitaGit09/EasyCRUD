FROM node:24-alpine

COPY . /opt/ 

WORKDIR /opt

RUN npm install && npm run build

RUN apk update && apk add apache2

#dist/index.html /var/www/localhost/htdocs/index.html

RUN rm -f /var/www/localhost/htdocs/*

RUN cp -rf dist/* /var/www/localhost/htdocs/ 

EXPOSE 80

CMD [ "httpd", "-D", "FOREGROUND" ]