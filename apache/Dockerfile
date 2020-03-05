FROM ubuntu:18.04

RUN apt-get update && apt-get install -y apache2 \
	&& apt-get -y install unzip \
	&& apt-get -y install nano \
    && apt-get -y install libapache2-mod-fcgid \
    && a2enmod proxy_fcgi

COPY 000-default.conf /etc/apache2/sites-available
COPY oscommerce-2.3.4.1.zip /var/www/html/

RUN unzip /var/www/html/oscommerce-2.3.4.1.zip -d /var/www/html/ \
	&& chmod 777 /var/www/html/oscommerce-2.3.4.1/catalog/includes/configure.php \
	&& chmod 777 /var/www/html/oscommerce-2.3.4.1/catalog/admin/includes/configure.php

    
EXPOSE 80
CMD ["apachectl", "-D", "FOREGROUND"]