FROM ubuntu:24.04

ENV LANG=en_US.UTF-8

RUN \
  export DEBIAN_FRONTEND=noninteractive && \
  apt update -y && \
  apt install -y locales && \
  locale-gen en_US.UTF-8 && \
  sysctl -w kernel.unprivileged_userns_clone=1 && \
  apt install -y \
    git \
    rsync && \
  chsh -s /bin/bash

SHELL ["/bin/bash", "-c"]
