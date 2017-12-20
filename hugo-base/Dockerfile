FROM centos:6
MAINTAINER "VTRyo" <vtryo.work@gmail.com>

# golang install
RUN yum install -y \
    wget \
    tar
WORKDIR /tmp
RUN wget https://storage.googleapis.com/golang/go1.4.2.linux-amd64.tar.gz \
    && tar -C /usr/local -xzf go1.4.2.linux-amd64.tar.gz
ENV PATH /usr/local/go/bin:$PATH

# for git
RUN yum install -y \
    curl-devel \
    expat-devel \
    gettext-devel \
    openssl-devel \
    zlib-devel \
    perl-ExtUtils-MakeMaker
RUN yum install -y gcc
WORKDIR /tmp
RUN wget https://www.kernel.org/pub/software/scm/git/git-2.3.4.tar.gz \
    && tar zxvf git-2.3.4.tar.gz \
    && cd git-2.3.4 && ./configure --prefix=/usr/local && make prefix=/usr/local all \
    && make prefix=/usr/local install

# hugo install with go command
