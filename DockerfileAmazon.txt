#---------------------------------------------------------------------------
# Dockefile to build Docker Image of Apache WebServer running on AmazonLinux 
#
# Made by Denis Astahov ADV-IT  13-March-2019
#---------------------------------------------------------------------------

FROM amazonlinux

RUN yum -y update
RUN yum -y install httpd

RUN echo 'Hello World from Docker!' > /var/www/html/index.html
CMD ["/usr/sbin/httpd","-D","FOREGROUND"]

EXPOSE 80
