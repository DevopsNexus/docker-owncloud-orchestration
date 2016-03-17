FROM centos:7
MAINTAINER Aditya Patawari <aditya@adityapatawari.com>

RUN yum -y update && yum clean all
RUN yum -y install epel-release http://rpms.famillecollet.com/enterprise/remi-release-7.rpm && yum clean all
RUN yum -y install --enablerepo remi-php56 httpd bzip2 php-xml php php-mbstring php-mysqlnd php-gd && yum clean all
ADD owncloud.conf /etc/httpd/conf.d/
WORKDIR /var/www/html
ADD https://download.owncloud.org/community/owncloud-9.0.0.tar.bz2 owncloud.tar.bz2
RUN tar -xjvf owncloud.tar.bz2
RUN chown -R apache owncloud
EXPOSE 80
CMD ["/sbin/httpd", "-D", "FOREGROUND"]
