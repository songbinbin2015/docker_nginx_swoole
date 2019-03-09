FROM nginx:1.13.3-alpine

ADD nginx.conf /etc/nginx/

ARG PHP_UPSTREAM=php-fpm
RUN echo "http://mirrors.ustc.edu.cn/alpine/v3.5/main" > /etc/apk/repositories \
&& echo "http://mirrors.ustc.edu.cn/alpine/v3.5/community" >> /etc/apk/repositories
RUN apk update \
    && apk upgrade \
    && apk add --no-cache bash \
    && adduser -D -H -u 1000 -s /bin/bash www-data \
    && rm /etc/nginx/conf.d/default.conf \
    && echo "upstream php-upstream { server ${PHP_UPSTREAM}:9000; }" > /etc/nginx/conf.d/upstream.conf

CMD ["nginx"]

EXPOSE 80 443
