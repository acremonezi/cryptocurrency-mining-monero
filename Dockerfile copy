FROM ubuntu:20.04

RUN set -ex && \
    apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get --no-install-recommends --yes install \
        apt-utils \
        automake \
        autotools-dev \
        bsdmainutils \
        build-essential \
        ca-certificates \
        ccache \
        cmake \
        curl \
        git \
        libtool \
        autoconf \
        pkg-config \
        gperf \
        libuv1-dev \
        libssl-dev \
        libhwloc-dev \ 
        nano \
        htop \
        wget

RUN mkdir -p /src
WORKDIR /src

RUN git clone https://github.com/xmrig/xmrig.git 
RUN cd xmrig/scripts && ./build_deps.sh
RUN mkdir -p xmrig/build && cd xmrig/build && cmake .. && make -j$(nproc)
