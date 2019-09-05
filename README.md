# ***DOCKER***

## BASE IMAGE MYSQL
/home/ariannebatac/Documents/docker-compose/php7.2-apache

## CHILD IMAGE
/home/ariannebatac/Documents/docker-compose/wordpress

## PHPMYADMIN IMAGE
/home/ariannebatac/Documents/docker-compose/phpmyadmin

## MySQL PATH
/var/databases/mysql
/var/lib/mysql

## PROJECT PATH
/var/www/web

## DOCKER PATH
/home/ariannebatac/Documents/docker-compose

## BUILD IMAGE
docker build -t=arianne/wordpress-apache-php:7.2 .

## DOCKER UP
docker-compose -f /home/ariannebatac/Documents/docker-compose/wordpress up -d

## IP ADDRESS INSIDE CONTAINER
docker inspect

## RUN APACHE INSIDE SSH
service apache2 start

## HOST CHANGE IP NAME
vim /etc/hosts

## ENTER CONTAINER SSH
docker exec -it 3cc218db6241 bash

## CREATE NETWORK
 docker network create \
  --driver=bridge \
  --subnet=192.168.0.0/16 \
  --ip-range=192.168.1.1/24 \
  --gateway=192.168.254.254 \
  devnetwork

## docker run --name=mysql5.6-192.168.1.2 --net=devnetwork --ip=192.168.116.2 -v /private/var/databases/mysql/5.6:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=ROOT -d -p 3306:3306 mysql:5.6
