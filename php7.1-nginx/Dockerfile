FROM ubuntu:16.04
MAINTAINER Jeff Claud <jefferson.claud@nuworks.ph>
RUN apt-get update -y
#RUN apt-get install -y python-software-properties software-properties-common
RUN apt-get install -y software-properties-common
#RUN apt-get install -y python-software-properties
RUN LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php
RUN apt-get update
#RUN add-apt-repository ppa:ondrej/php
RUN apt-get update
RUN apt-get install --allow-unauthenticated -y nginx php7.1
RUN apt-get install --allow-unauthenticated -y php7.1-mbstring php7.1-mcrypt php7.1-tokenizer php7.1-curl php7.1-dom zip vim nano php7.1-fpm php-mysql wkhtmltopdf libxrender1 php7.1-imap git cron openssl php-bcmath
RUN echo "\ndaemon off;" >> /etc/nginx/vhost-nginx.conf
RUN sed -i -e "s/;\?daemonize\s*=\s*yes/daemonize = no/g" /etc/php/7.1/fpm/php-fpm.conf
RUN echo "\ncgi.fix_pathinfo=0" >> /etc/php/7.1/fpm/php.ini
RUN echo "\nupload_max_filesize = 100M" >> /etc/php/7.1/fpm/php.ini
RUN echo "\npost_max_size = 100M" >> /etc/php/7.1/fpm/php.ini
# Nginx config
RUN rm /etc/nginx/sites-enabled/default
ADD ./vhost-nginx.conf /etc/nginx/sites-available/
RUN ln -s /etc/nginx/sites-available/vhost-nginx.conf /etc/nginx/sites-enabled/vhost-nginx
# WEB SERVER ENVIRONMENT
ENV RUN_USER www-data
ENV RUN_GROUP www-data
# PHP config
#RUN sed -i -e "s/;\?date.timezone\s*=\s*.*/date.timezone = Europe\/Kiev/g" /etc/php/fpm/php.ini
# Expose ports.
EXPOSE 80
# Copy this repo into place.
#ADD src /var/www/site
#mkdir /var/www/site
# Define default command.
#CMD sudo service php7.1-fpm start && nginx
#CMD cron && tail -f /var/log/cron.log

ENTRYPOINT ["/bin/bash"]
