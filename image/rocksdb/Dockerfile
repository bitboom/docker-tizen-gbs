FROM ubuntu:16.04
MAINTAINER sangwan.kwon@samsung.com

# intall tool-chain
RUN apt-get update && \
    apt-get -qq install build-essential cmake git

# install dependencies
RUN apt-get -qq install libgflags-dev libsnappy-dev zlib1g-dev \
                        libbz2-dev liblz4-dev libzstd-dev

# download rocksdb
RUN cd /usr/src && git clone https://github.com/facebook/rocksdb.git 

# build rocksdb
RUN cd /usr/src/rocksdb && make all

# install rocksdb // This makes build-fail when run in dockerfile
# RUN make install
