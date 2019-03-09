##FROM registry.cn-beijing.aliyuncs.com/ttmama/php-alpine-docker:php-7.1.8-alpine-redis
FROM php:7.3.3-fpm-alpine3.9
COPY ./sources.list /etc/apt/sources.list
RUN apt-get update && apt-get install -y \
zlib1g-dev \
&& apt-get clean \
&& pecl install swoole \
&& docker-php-ext-enable swoole
