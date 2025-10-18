ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Copy data for add-on
COPY rootfs /

RUN apk update
RUN apk add --no-cache \
    snapcast snapcast-server snapcast-client \
    librespot \
    alsa-plugins-pulse
#RUN apk add --no-cache neovim screen

