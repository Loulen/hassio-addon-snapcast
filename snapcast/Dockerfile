FROM ghcr.io/linuxserver/baseimage-alpine:edge

# set version label
ARG BUILD_DATE
ARG VERSION
LABEL build_version="version:- ${VERSION} Build-date:- ${BUILD_DATE}"
LABEL maintainer="llenoir"


SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN set -ex \
  echo "**** setup apk testing mirror ****" \
  && echo "@testing http://nl.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories \
  && cat /etc/apk/repositories \
  && echo "**** install runtime packages ****" \
  && apk add --no-cache -U --upgrade \
    alsa-utils \
    librespot@testing \
    shairport-sync@testing \
    snapcast \
  && echo "**** cleanup ****" \
  && rm -rf \
    /tmp/*


# Copy data for add-on
COPY rootfs /