FROM ubuntu:14.04
MAINTAINER Iader E. Garcia Gomez <iadergg@gmail.com>

RUN apt-get update && apt-get install -y apache2 && apt-get clean && rm -rf /var/lib/apt/lists/*

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2

WORKDIR /var/www

EXPOSE 2224

RUN apt-get update 
RUN apt-get -y install software-properties-common
RUN add-apt-repository ppa:ondrej/php
RUN apt-get update 
RUN apt-get --force-yes install php5

RUN mkdir /var/www/html/moodle
RUN mkdir /var/www/moodledata

ADD ["index.php","/var/www/html/"]
ADD ["", "/var/www/"]

ENTRYPOINT ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]