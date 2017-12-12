FROM centos:6
MAINTAINER "VTRyo" <vtryo.work@gmail.com>

#upgrade section
ADD ./templates/h2o/bintray-tatsushid-h2o-rpm.repo /etc/yum.repos.d/bintray-tatsushid-h2o-rpm.repo
RUN yum -y update

# base install section
RUN yum -y install \
    vim \
    git \
    curl \
    wget \
    whchi \
    tar

# h2o install section
RUN yum -y install h2o
RUN mkdir /etc/h2o/mruby
ADD ./templates/h2o/mruby/htpasswd.rb /etc/h2o/mruby/htpasswd.rb

#wordpress section
RUN mkdir -p /var/www/html
WORKDIR /var/www/html
RUN git clone --depth=1 https://github.com/WordPress/WordPress.git

#php section
RUN rpm -Uvh \
    https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm \
    http://rpms.famillecollet.com/enterprise/remi-release-6.rpm

RUN yum -y install \
    libwebp


