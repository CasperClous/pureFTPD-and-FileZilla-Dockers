FROM ubuntu

WORKDIR /pure_FTP

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get -yqq update \
&& apt-get -y upgrade \
&& apt-get -y install build-essential \
&& apt-get -y install libplib-dev \
&& apt-get -y install apt-utils \
&& apt-get -y install make \
&& apt-get -y install -y autoconf-archive \
&& apt-get -y install -y git \
&& apt-get -y install -y automake \
&& git clone https://github.com/jedisct1/pure-ftpd.git \
&& cd pure-ftpd \
&& aclocal \
&& autoreconf -vfi \
&& automake -a \
&& ./configure \
&& make -j4 \
&& make install

ENTRYPOINT ["/usr/local/sbin/pure-ftpd &"]