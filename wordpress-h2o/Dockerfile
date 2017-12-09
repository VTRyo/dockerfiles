FROM centos:6
MAINTAINER "VTRyo" <vtryo.work@gmail.com>

#upgrade section
ADD ./templates/h2o/bintray-tatsushid-h2o-rpm.repo /etc/yum.repos.d/bintray-tatsushid-h2o-rpm.repo
RUN yum update -y

# base install section
RUN yum -y install vim
RUN yum -y install git
RUN yum -y install curl
RUN yun -y install wget
RUN yum install -y which
RUN yum install -y wget
RUN yum install -y tar

# h2o install section
RUN yum -y install h2o
RUN mkdir /etc/h2o/mruby
ADD ./templates/h2o/mruby/htpasswd.rb /etc/h2o/mruby/htpasswd.rb

#wordpress
RUN mkdir -p /var/www/html
ADD ./templates/wordpress/wordpress-4.9.1-ja.tar.gz /var/www/html/wordpress-4.9.1-ja.tar.gz
RUN tar -zxvf /var/www/html/wordpress-4.9.1-ja.tar.gz
RUN rm -rf /var/www/html/wordpress-4.9.1-ja.tar.gz
