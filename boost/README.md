# Dockerize boost

> [Boost][1] provides free peer-reviewed portable C++ source libraries

Dockerize boost on linux (ubuntu 16.04).

### HOST
1. Pull docker image from [docker-hub][2].
```sh
$ docker pull bitboom/boost
```

2. Run docker image (network and volume is options)
```sh
$ docker run --rm -it bitboom/boost /bin/bash
```
### Docker
3. Build example codes
```sh
$ cd /usr/src/boost_1_66_0/libs/coroutine2/example
$ g++ fibonacci.cpp -std=c++1y -L/usr/lib -lboost_coroutine -lboost_context
```

## Ref
Boost with [CMake][3]
[1]:https://boost.org/
[2]:https://hub.docker.com/r/bitboom/boost/
[3]:https://cmake.org/cmake/help/v3.0/module/FindBoost.html
