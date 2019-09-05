# DOCKER

### BASE IMAGE MYSQL
```php
docker-compose/php7.2-apache
```

### CHILD IMAGE
```php
docker-compose/wordpress
```

### PHPMYADMIN IMAGE
```php
docker-compose/phpmyadmin
```

### MySQL PATH
```php
/var/databases/mysql
/var/lib/mysql
```

### PROJECT PATH
```php
/var/www/web
```

### DOCKER PATH
```php
docker-compose
```

### BUILD IMAGE
```php
docker build -t=arianne/wordpress-apache-php:7.2 .
```

### DOCKER UP
```php
docker-compose -f docker-compose/wordpress up -d
```

### IP ADDRESS INSIDE CONTAINER
```php
docker inspect
```

### RUN APACHE/NGINX INSIDE SSH
```php
service apache2 start
service nginx start
```

### HOST CHANGE IP NAME
```php
vim /etc/hosts
```

### ENTER CONTAINER SSH
```php
docker exec -it container_name bash
```

### CREATE NETWORK
```php
 docker network create \
  --driver=bridge \
  --subnet=192.168.0.0/16 \
  --ip-range=192.168.1.1/24 \
  --gateway=192.168.254.254 \
  devnetwork
```
### CREATE MYSQL5.6
```php
docker run --name=mysql5.6-192.168.1.2 --net=devnetwork --ip=192.168.116.2 -v /private/var/databases/mysql/5.6:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=ROOT -d -p 3306:3306 mysql:5.6
```
