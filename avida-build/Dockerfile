FROM ubuntu:20.04 as avida-builder
ARG DEBIAN_FRONTEND=noninteractive
WORKDIR /github.com/fortunalab/
RUN apt-get update  && apt-get install -y \
    gcc-9 \
    g++-9 \
    cmake=3.16.3-1ubuntu1 \
    make=4.2.1-1.2 \
    git=1:2.25.1-1ubuntu3.4 \
    curl \
&& update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 100 \
&& update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-9 100 \ 
&& git clone https://github.com/fortunalab/avida.git
WORKDIR /github.com/fortunalab/avida
RUN git submodule update --init --recursive
RUN ./build_avida

FROM ubuntu:20.04
WORKDIR /avida/
COPY --from=avida-builder /github.com/fortunalab/avida/cbuild/work/ .
