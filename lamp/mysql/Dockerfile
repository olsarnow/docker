FROM ubuntu:latest
MAINTAINER Olaf Sarnow <olaf@sarnow.no>


ENV MYSQL_USER=mysql \
    MYSQL_DATA_DIR=/var/lib/mysql \
    MYSQL_RUN_DIR=/run/mysqld \
    MYSQL_LOG_DIR=/var/log/mysql \
	MYSQL_ROOT_PASSWORD=rootpassword

RUN apt-get update && apt-get -y upgrade && DEBIAN_FRONTEND=noninteractive apt-get -y install mysql-server

# COPY entrypoint.sh /sbin/entrypoint.sh

# RUN chmod 755 /sbin/entrypoint.sh

EXPOSE 3306/tcp

# ENTRYPOINT ["/sbin/entrypoint.sh"]

CMD ["/usr/bin/mysqld_safe"]
