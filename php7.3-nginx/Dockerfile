FROM jclaud/nginx-php:7.2
RUN apt update -y

RUN apt purge php* -y && apt autoremove -y && apt autoclean -y
RUN apt install php7.3 php7.3-fpm php7.3-common php7.3-mysql php7.3-sqlite php7.3-xml php7.3-xmlrpc php7.3-curl php7.3-gd php7.3-imagick php7.3-cli php7.3-dev php7.3-imap php7.3-mbstring php7.3-opcache php7.3-soap php7.3-zip php7.3-intl -y

RUN echo "\ncgi.fix_pathinfo=0" >> /etc/php/7.3/fpm/php.ini
RUN echo "\nupload_max_filesize = 100M" >> /etc/php/7.3/fpm/php.ini
RUN echo "\npost_max_size = 100M" >> /etc/php/7.3/fpm/php.ini

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

# Define default command.
CMD sudo service php7.3-fpm start && nginx
CMD cron && tail -f /var/log/cron.log
#RUN service php7.3-fpm start
#RUN service php7.3-fpm restart

ENTRYPOINT ["/bin/bash"]
