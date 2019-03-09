FROM mysql:5.7

MAINTAINER Mahmoud Zalt <mahmoud@zalt.me>

ADD startup /etc/mysql/startup

RUN chown -R mysql:root /var/lib/mysql/

ARG MYSQL_DATABASE=homesteadxx
ARG MYSQL_USER=homesteadxx
ARG MYSQL_PASSWORD=682sHF68S
ARG MYSQL_ROOT_PASSWORD=682sHF68S

ENV MYSQL_DATABASE=homesteadxx
ENV MYSQL_USER=homesteadxx
ENV MYSQL_PASSWORD=682sHF68S
ENV MYSQL_ROOT_PASSWORD=682sHF68S

RUN sed -i 's/MYSQL_DATABASE/'$MYSQL_DATABASE'/g' /etc/mysql/startup && \
    sed -i 's/MYSQL_USER/'$MYSQL_USER'/g' /etc/mysql/startup && \
    sed -i 's/MYSQL_PASSWORD/'$MYSQL_PASSWORD'/g' /etc/mysql/startup

ADD my.cnf /etc/mysql/conf.d/my.cnf

CMD ["mysqld", "--init-file=/etc/mysql/startup"]

EXPOSE 3306
