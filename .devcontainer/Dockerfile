# [Choice] Debian / Ubuntu version (use Debian 11, Ubuntu 18.04/22.04 on local arm64/Apple Silicon): debian-11, debian-10, ubuntu-22.04, ubuntu-20.04, ubuntu-18.04
ARG VARIANT="ubuntu-22.04"
FROM mcr.microsoft.com/vscode/devcontainers/cpp:0-${VARIANT}

RUN apt-get update && \
    apt-get -y install cmake gcc-arm-none-eabi gdb-multiarch
WORKDIR /apps
RUN git clone -b master https://github.com/raspberrypi/pico-sdk.git --depth=1 && \
    cd pico-sdk && \
    git submodule update --init 
ENV PICO_SDK_PATH=/apps/pico-sdk
