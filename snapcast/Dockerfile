ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Copy data for add-on
COPY rootfs /

RUN apk update
RUN apk add --no-cache openrc
RUN apk add --no-cache snapcast snapcast-server snapcast-client
RUN apk add --no-cache librespot
RUN apk add --no-cache alsa-plugins-pulse
#RUN apk add --no-cache neovim screen

