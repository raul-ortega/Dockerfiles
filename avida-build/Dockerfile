FROM ubuntu:20.04
ARG DEBIAN_FRONTEND=noninteractive
WORKDIR /github.com/fortunalab/
RUN apt-get update \
      && apt-get install -y gcc-9 g++-9 \
      && update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 100 \
      && update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-9 100 \
      && apt-get install -y cmake=3.16.3-1ubuntu1 \
      && apt-get install -y make=4.2.1-1.2 \
      && apt-get install -y git=1:2.25.1-1ubuntu3.4 \
      && git clone https://github.com/fortunalab/avida.git
WORKDIR /github.com/fortunalab/avida
RUN git submodule update --init --recursive
