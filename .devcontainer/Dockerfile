FROM mcr.microsoft.com/vscode/devcontainers/base:0-bullseye

RUN sed -i 's:deb.debian.org:ftp.cn.debian.org:g' /etc/apt/sources.list \
    && sed -i 's:security.debian.org:ftp.cn.debian.org:g' /etc/apt/sources.list

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    bash-completion \
    cloud-image-utils \
    qemu-utils \
    && apt-get -y clean && rm -rf /var/lib/apt/lists/*

RUN mkdir /images \
    && cd /images \
    && curl -sSL https://cloud.debian.org/images/cloud/bullseye/latest/debian-11-generic-amd64.qcow2 -O