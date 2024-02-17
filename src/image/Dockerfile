FROM ubuntu:24.04

ENV LANG=en_US.UTF-8 \
    TZ=Etc/UTC

RUN \
  export DEBIAN_FRONTEND=noninteractive && \
  echo 'tzdata tzdata/Areas select Etc' | debconf-set-selections && \
  echo 'tzdata tzdata/Zones/Etc select UTC' | debconf-set-selections && \
  apt update -y && \
  apt install -y locales && \
  locale-gen en_US.UTF-8 && \
  sysctl -w kernel.unprivileged_userns_clone=1 && \
  apt install -y \
    git \
    rsync \
    tzdata && \
  ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && \
  echo $TZ > /etc/timezone && \
  chsh -s /bin/bash

SHELL ["/bin/bash", "-c"]
