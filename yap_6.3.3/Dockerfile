FROM ubuntu:14.04

MAINTAINER Nuno Mendes gugas93@hotmail.com

RUN apt-get update && apt-get install -y wget \
	&& mkdir yap-6.3.3 && wget https://github.com/vscosta/yap-6.3/archive/yap-6.3.3.tar.gz \
	&& tar -xpvf yap-6.3.3.tar.gz -C yap-6.3.3 --strip-components 1 && rm yap-6.3.3.tar.gz \ 
	&& apt purge -y wget

RUN apt-get update && apt-get install -y libboost-all-dev \
    libgsl0ldbl build-essential && cd yap-6.3.3 && mkdir arch && cd arch \
    && ../configure --enable-tabling=yes --enable-dynamic-loading --with-readline=no \
    && make && make install && make install_library && apt purge -y libboost-all-dev \
    libgsl0ldbl build-essential && rm -rf /var/lib/apt/lists/*


