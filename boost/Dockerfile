FROM ubuntu:16.04
MAINTAINER sangwan.kwon@samsung.com

# gcc-6
RUN apt-get update && \
    apt-get install -y build-essential software-properties-common && \
    add-apt-repository ppa:ubuntu-toolchain-r/test -y && \
    apt-get update && \
    apt-get install -y gcc-6 g++-6 && \
    update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-6 60 \
                        --slave /usr/bin/g++ g++ /usr/bin/g++-6

# boost 
RUN apt-get install -y wget build-essential python-dev autotools-dev \
                       libicu-dev build-essential libbz2-dev libboost-all-dev && \
    cd /usr/src && \
    wget -O boost.tar.gz \
            https://dl.bintray.com/boostorg/release/1.66.0/source/boost_1_66_0.tar.gz && \
    tar xvzf boost.tar.gz && \
    cd /usr/src/boost_1_66_0 && \
    ./bootstrap.sh --prefix=/usr && \
    ./b2 toolset=gcc cxxflags=-std=c++14 && \
    ./b2 install
