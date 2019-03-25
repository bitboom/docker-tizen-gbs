FROM ubuntu:14.04
MAINTAINER sangwan.kwon@samsung.com

RUN echo "deb http://download.tizen.org/tools/latest-release/Ubuntu_14.04/ /" >> /etc/apt/sources.list
RUN apt-get update
RUN apt-get -qq --force-yes install gbs
RUN apt-get -qq install qemu binfmt-support qemu-user-static

COPY gbs.conf /root/.gbs.conf
