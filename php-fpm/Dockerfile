FROM php:7.4.3-fpm
COPY --from=composer /usr/bin/composer /usr/bin/composer
COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/
RUN echo "deb http://mirrors.aliyun.com/debian/ buster main non-free contrib\
    deb-src http://mirrors.aliyun.com/debian/ buster main non-free contrib\
    deb http://mirrors.aliyun.com/debian-security buster/updates main\
    deb-src http://mirrors.aliyun.com/debian-security buster/updates main\
    deb http://mirrors.aliyun.com/debian/ buster-updates main non-free contrib\
    deb-src http://mirrors.aliyun.com/debian/ buster-updates main non-free contrib\
    deb http://mirrors.aliyun.com/debian/ buster-backports main non-free contrib\
    deb-src http://mirrors.aliyun.com/debian/ buster-backports main non-free contrib" >  /etc/apt/sources.list\
    && apt-get update\ 
    && apt-get install -y git\
    && install-php-extensions gd pdo_mysql zip
CMD php-fpm