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

RUN yum -y install \
    httpd \
    libmcrypt \
    libtool-ltdl \
    libtidy \
    libXpm \
    libtiff \
    autoconf \
    automake \
    gd-last \
    enchant-aspell

RUN yum -y install --enablerepo=remi,remi-php70 \
    php \
    php-process \
    php-mysqlnd \
    php-pecl-mailparse \
    php-json \
    php-cli \
    php-pdo \
    php-fpm \
    php-bcmath \
    php-gd \
    php-mcrypt \
    php-pecl-apcu \
    php-pecl-igbinary \
    php-pear \
    php-intl \
    php-pecl-apcu-devel \
    php-common \
    php-mbstring \
    php-xml \
    php-devel \
    php-pecl-apcu-bc \
    php-pecl-redis \
    php-opcache \
    php-enchant
