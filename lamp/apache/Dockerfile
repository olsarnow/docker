FROM ubuntu:latest
MAINTAINER Olaf Sarnow <olaf@sarnow.no>

RUN apt-get update && apt-get -y upgrade && DEBIAN_FRONTEND=noninteractive apt-get -y install \
    apache2

RUN a2enmod rewrite
RUN a2enmod deflate
RUN a2enmod proxy
RUN a2enmod proxy_fcgi


ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid

EXPOSE 80

ADD apache-config.conf /etc/apache2/sites-enabled/000-default.conf

CMD /usr/sbin/apache2ctl -D FOREGROUND