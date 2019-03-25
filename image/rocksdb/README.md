# Dockerize rocksdb

> [RocksDB][1] is an embeddable persistent key-value store for fast storage.  

Dockerize rocksdb on linux (ubuntu 16.04).

### HOST
1. Pull docker image from [docker-hub][2].
```sh
$ docker pull bitboom/rocksdb
```

2. Run docker image (network and volume is options)
```sh
$ docker run --rm -it --network=host -v ${HOST_SRC_DIR}:${DOCKER_SRC_DIR} bitboom/rocksdb /bin/bash
```
### Docker
3. Test rocksdb & Build code using g++
```sh
$ cd /usr/src/rocksdb && make check
$ g++ ${src}.cpp -std=c++11 -lrocksdb -lsnappy -lzstd \
                            -llz4 -lbz2 -lz -pthread
```

[1]:https://rocksdb.org/
[2]:https://hub.docker.com/r/bitboom/rocksdb/
