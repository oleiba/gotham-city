FROM ubuntu:xenial
LABEL maintainer="g.benattar@gmail.com"
LABEL description="This is the build stage for Gotham server"

RUN apt-get update && apt-get install -y \
    build-essential \
    make \
    g++ \
    curl \
    clang \
    libgmp3-dev

ARG CHANNEL="nightly"
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y --default-toolchain ${CHANNEL}

ENV rocket_address=0.0.0.0
ENV rocket_port=8080

ADD gotham-server /app
WORKDIR /app
