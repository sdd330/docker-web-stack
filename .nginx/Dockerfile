## Version: 0.4
FROM centos:centos6
MAINTAINER Anton Bugreev <anton@bugreev.ru>

## create user dev
RUN useradd dev -u 1000

## nginx
RUN rpm -Uvh http://nginx.org/packages/centos/6/noarch/RPMS/nginx-release-centos-6-0.el6.ngx.noarch.rpm
RUN yum install nginx which -y 
COPY ./etc/nginx/nginx.conf /etc/nginx/nginx.conf

### etc
## set timezone
RUN cp -f /usr/share/zoneinfo/Asia/Novosibirsk /etc/localtime

### volumes
## nginx virtual hosts
VOLUME ["/etc/nginx/hosts/"]

## web
VOLUME ["/home/dev/logs/"]
VOLUME ["/home/dev/www/"]

### main
CMD ["/usr/sbin/nginx"]

### allow ports 
EXPOSE 80
EXPOSE 443

