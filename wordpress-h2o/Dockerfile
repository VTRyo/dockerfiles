FROM centos:6
MAINTAINER "VTRyo" <vtryo.work@gmail.com>

#upgrade section
ADD ./templates/h2o/bintray-tatsushid-h2o-rpm.repo /etc/yum.repos.d/bintray-tatsushid-h2o-rpm.repo
RUN yum -y update

# base install section
RUN yum -y install vim
RUN yum -y install git
RUN yum -y install curl
RUN yum -y install wget
RUN yum -y install which
RUN yum -y install wget
RUN yum -y install tar

# h2o install section
RUN yum -y install h2o
RUN mkdir /etc/h2o/mruby
ADD ./templates/h2o/mruby/htpasswd.rb /etc/h2o/mruby/htpasswd.rb

#wordpress
RUN mkdir -p /var/www/html
WORKDIR /var/www/html
RUN git clone --depth=1 https://github.com/WordPress/WordPress.git
