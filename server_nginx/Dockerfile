FROM centos:centos7
MAINTAINER rohanjayrajmohite

RUN yum -y update; yum clean all
RUN yum -y install http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm; yum -y makecache
RUN yum -y install nginx-1.8.0

RUN rm /etc/nginx/conf.d/default.conf
RUN rm /etc/nginx/conf.d/example_ssl.conf

COPY conf/server.conf /etc/nginx/conf.d/server.conf
COPY conf/nginx.conf /etc/nginx/nginx.conf

# Backend not found html response
COPY ./backend-not-found.html /var/www/html/backend-not-found.html

EXPOSE 80

CMD ["nginx"]

