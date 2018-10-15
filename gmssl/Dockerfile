FROM ubuntu:18.04

ADD ./sources.list /etc/apt/sources.list
ADD ./GmSSL /data/app/GmSSL
ADD ./php-src /data/app/php-src

RUN set -x \
	&& apt update \
	&& apt install -y vim gcc g++ perl autoconf re2c bison libxml2-dev libsqlite3-dev make wget git \
	&& (cd /data/app/GmSSL;pwd; /data/app/GmSSL/config --prefix=/usr/local/gmssl no-saf no-sdf no-skf no-sof no-zuc && make 1>make.log && make install 1>make_install.log ) \
	&& ls



WORKDIR /data/app

CMD /bin/bash
