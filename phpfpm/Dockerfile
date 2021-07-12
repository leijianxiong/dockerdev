FROM php:7.4-fpm

#安装扩展
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN chmod +x /usr/local/bin/install-php-extensions && sync && \
    install-php-extensions @composer bcmath bz2 gd gettext intl mcrypt memcached mysqli pcntl pdo_mysql \
      protobuf redis shmop soap sockets sysvmsg sysvsem sysvshm vips xmlrpc zip xdebug

# install git for feature command `compose install`
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y git