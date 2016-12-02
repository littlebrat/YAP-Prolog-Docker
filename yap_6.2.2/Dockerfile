FROM ubuntu:14.04

MAINTAINER Nuno Mendes gugas93@hotmail.com

RUN apt-get update && apt-get install -y wget \
	&& wget http://www.dcc.fc.up.pt/~vsc/Yap/yap-6.2.2.tar.gz \
	&& tar -xpvf yap-6.2.2.tar.gz && rm yap-6.2.2.tar.gz \ 
	&& apt purge -y wget

RUN apt-get update && apt-get install -y libboost-all-dev \
    build-essential && cd yap-6.2.2 && mkdir arch && cd arch \
    && ../configure --enable-tabling=yes --enable-dynamic-loading --with-readline=no \
    && make && make install && make install_library && apt purge -y libboost-all-dev \
    build-essential && rm -rf /var/lib/apt/lists/*


