FROM apache-php:7.0


# Setup WordPress Unit Testing

RUN curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
RUN chmod +x wp-cli.phar
RUN mv wp-cli.phar /usr/local/bin/wp

############################
## ADDITIONAL NOTES        #
############################
# RUN later
# wp scaffold plugin-tests your-plugin-name
# cd path-to-wordpress-plugin
# bash bin/install-wp-tests.sh test_wordpress_tutorial root root 192.168.0.1 latest

