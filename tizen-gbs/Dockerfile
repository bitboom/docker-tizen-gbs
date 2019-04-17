FROM ubuntu:16.04
MAINTAINER sangwan.kwon@samsung.com

RUN echo "deb [trusted=yes] http://download.tizen.org/tools/latest-release/Ubuntu_16.04/ /" >> /etc/apt/sources.list
RUN apt-get update && apt-get -qq install gbs

COPY gbs.conf /root/.gbs.conf

ENTRYPOINT ["/bin/bash"]
