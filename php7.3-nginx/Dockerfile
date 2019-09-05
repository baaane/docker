FROM jclaud/nginx-php:7.2
RUN apt update -y

RUN apt purge php* -y && apt autoremove -y && apt autoclean -y
RUN apt install php7.3 php7.3-fpm php7.3-common php7.3-mysql php7.3-sqlite php7.3-xml php7.3-xmlrpc php7.3-curl php7.3-gd php7.3-imagick php7.3-cli php7.3-dev php7.3-imap php7.3-mbstring php7.3-opcache php7.3-soap php7.3-zip php7.3-intl -y

RUN service php7.3-fpm start
RUN service php7.3-fpm restart
