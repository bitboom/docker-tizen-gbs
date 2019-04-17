# Dockerize tizen build system

[GBS][1] is local build system for tizen platform developer.  
Dockerize gbs for building tizen at docker.

### HOST
1. Pull docker image from [docker-hub][2].
```sh
$ docker pull bitboom/tizen-gbs
```

2. Download tizen-source-code at host PC.
3. Run docker image by using volume.
```sh
$ docker run --rm -it --net=host --privileged \
             -v ${HOST_DIR}:/usr/src bitboom/tizen-gbs
```
### Docker
4. Build tizen-source-code with GBS.
```sh
$ cd /usr/src
$ gbs build -A armv7l -P standard
```

[1]:https://source.tizen.org/documentation/reference/git-build-system
[2]:https://hub.docker.com/r/bitboom/tizen-gbs/
