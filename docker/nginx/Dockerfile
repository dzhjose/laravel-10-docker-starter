FROM nginx:stable-alpine

ARG UID
ARG GID

ENV UID=${UID}
ENV GID=${GID}

RUN addgroup -g ${GID} --system laravel
RUN adduser -G laravel --system -D -s /bin/sh -u ${UID} laravel
RUN sed -i "s/user  nginx/user laravel/g" /etc/nginx/nginx.conf

ADD ./docker/nginx/default.conf /etc/nginx/conf.d/
ADD ./docker/nginx/nginx.conf /etc/nginx/nginx.conf

RUN mkdir -p /var/www/html