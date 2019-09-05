FROM ubuntu:16.04

Maintainer Jefferson Claud<jefferson.claud@nuworks.ph>

RUN apt-get -y --fix-missing update
# Install apache, PHP, and supplimentary programs, openssh-server, curl, and lynx-cur
RUN apt-get -y --force-yes install software-properties-common python-software-properties

RUN LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php


RUN apt-get -y update && apt-cache pkgnames | grep php7.0 && apt-get -y install apache2 php7.0
RUN apt-get -y --fix-missing update
RUN apt-get -y install php7.0-cli php7.0-gd php7.0-intl php7.0-common php7.0-mysql php7.0-curl curl \
lynx-cur php7.0-dom zip unzip php7.0-xml \
php7.0-zip php7.0-mbstring libapache2-mod-php php-mcrypt \
php7.0-json php7.0-opcache php7.0-dev php7.0-sqlite git && apt-cache search php7.0 && apt-get -y --fix-missing update \
&& curl -sS https://getcomposer.org/installer -o composer-setup.php && curl -s https://getcomposer.org/installer | php \
&& mv composer.phar /usr/local/bin/composer && apt-get install sqlite3 libsqlite3-dev \
wget subversion mysql-client vim -y


ADD ./vhost.conf /etc/apache2/sites-available/

RUN a2enmod rewrite
RUN a2dissite 000-default.conf

RUN a2ensite vhost.conf


EXPOSE 80

ENTRYPOINT ["/bin/bash"]

