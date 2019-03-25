FROM ubuntu:16.04
MAINTAINER sangwan.kwon@samsung.com

# intall tool-chain
RUN apt-get update && \
    apt-get -qq install build-essential cmake git

# install dependencies
RUN apt-get -qq install libsnappy-dev zlib1g-dev \
                        libbz2-dev liblz4-dev libzstd-dev

# download rocksdb
RUN cd /usr/src && git clone https://github.com/facebook/rocksdb.git 

# build && install rocksdb
RUN cd /usr/src/rocksdb && make static_lib && make install
