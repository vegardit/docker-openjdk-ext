#syntax=docker/dockerfile:1.2
# Copyright 2020-2021 by Vegard IT GmbH, Germany, https://vegardit.com
# SPDX-License-Identifier: Apache-2.0
#
# Author: Sebastian Thomschke, Vegard IT GmbH
#
# https://github.com/vegardit/docker-openjdk-ext
#

# https://github.com/docker-library/openjdk/blob/master/8/jre/slim-buster/Dockerfile
ARG BASE_IMAGE=openjdk:8-jre-slim

FROM ${BASE_IMAGE}

LABEL maintainer="Vegard IT GmbH (vegardit.com)"

USER root

SHELL ["/bin/bash", "-c"]

# if set to 1 debug tools are added to the image (htop,less,mc,vim)
ARG DEBUG_BUILD=0

ARG DEBIAN_FRONTEND=noninteractive
ARG LC_ALL=C

ARG BASE_LAYER_CACHE_KEY

RUN --mount=type=bind,source=.shared,target=/mnt/shared \
  set -eu && \
  /mnt/shared/cmd/debian-install-os-updates.sh && \
  /mnt/shared/cmd/debian-install-support-tools.sh && \
  #
  echo "#################################################" && \
  echo "Installing tools..." && \
  echo "#################################################" && \
  apt-get install --no-install-recommends -y curl git less procps && \
  #
  echo "#################################################" && \
  echo "Installing latest Docker client..." && \
  echo "#################################################" && \
  docker_cli_package=$(curl -fLsS https://download.docker.com/linux/static/stable/x86_64/ | grep -oP '(?<=>)docker-\d+.\d+.\d+.tgz(?=</a>)' | tail -1) && \
  docker_cli_download_url=https://download.docker.com/linux/static/stable/x86_64/$docker_cli_package && \
  echo "Downloading [$docker_cli_download_url]..." && \
  curl -fL $docker_cli_download_url | tar zxv -C /usr/bin --strip-components=1 docker/docker && \
  apt-get install --no-install-recommends -y binutils && \
  strip -s /usr/bin/docker && \
  apt-get remove -y binutils && \
  #
  /mnt/shared/cmd/debian-cleanup.sh

ARG BUILD_DATE
ARG GIT_COMMIT_HASH
ARG GIT_REPO_URL

LABEL \
 org.label-schema.schema-version="1.0" \
 org.label-schema.build-date=$BUILD_DATE \
 org.label-schema.vcs-ref=$GIT_COMMIT_HASH \
 org.label-schema.vcs-url=$GIT_REPO_URL
