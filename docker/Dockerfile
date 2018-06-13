FROM ubuntu:16.04

RUN apt-get update -y
RUN apt-get install apache2 -y
 


RUN apt-get install software-properties-common -y
RUN LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php -y
RUN apt-get update -y
RUN apt install php7.2 php7.2-cli php7.2-common php7.2-json php7.2-opcache php7.2-mysql php7.2-mbstring php7.2-zip php7.2-fpm php7.2-xml libapache2-mod-php -y

RUN apt install curl
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN composer global require "laravel/installer"

COPY 000-default.conf /etc/apache2/sites-available/000-default.conf

RUN a2enmod rewrite

EXPOSE 80

CMD apachectl -D FOREGROUND