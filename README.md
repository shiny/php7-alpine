# php7-alpine

composer is enabled. `docker-compose run php compose`

Enabled extra extensions are (which not enabled default in PHP official version):
- bcmath 
- mcrypt 
- zip 
- bz2 
- pdo_mysql 
- mysqli 
- simplexml 
- opcache 
- sockets 
- mbstring 
- pcntl 
- xsl
- gd
- imagick

## docker-compose.yml

```yml
version: '2'
services:
  php:
    image: "daijie/php7-alpine"
    volumes:
      - ./src:/var/www
```

- You can specify wwwroot dir in volumes, mapping to `/var/www`
- docker-compose will create ./src if it does not exists

## specify your own php.ini/php-fpm.conf
Place your php.ini and php-fpm.conf into the same dir of docker-compose.yml

```yml
version: '2'
services:
  php:
    image: "daijie/php7-alpine"
    volumes:
      - ./src:/var/www
      - ./php.ini:/usr/local/etc/php/php.ini
      - ./php-fpm.conf:/usr/local/etc/php-fpm.d/www.conf
```

## Enable other extensions
You can fork and modify this Dockerfile
