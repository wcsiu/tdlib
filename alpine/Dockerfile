FROM alpine:3.15

WORKDIR /

RUN apk add --no-cache \
        ca-certificates

RUN apk add --no-cache --virtual .build-deps \
        g++ \
        make \
        cmake \
        git \
        gperf \
        libressl-dev \
        zlib-dev \
        zlib-static \
        linux-headers;

RUN git clone https://github.com/tdlib/td.git && \
    cd td && \
    git checkout v1.8.0 && \
    mkdir build && \
    cd build && \
    cmake -DCMAKE_BUILD_TYPE=Release .. && \
    cmake --build . && \
    make install