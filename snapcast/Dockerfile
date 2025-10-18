ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG=C.UTF-8

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Copy data for add-on
COPY rootfs /

RUN apk update
RUN apk add --no-cache openrc
RUN apk add --no-cache snapcast snapcast-server snapcast-client
# librespot not available in Alpine v3.16 base repositories; omitted.
# If present in image (/usr/bin/librespot), the run script will enable it.
RUN apk add --no-cache alsa-plugins-pulse
#RUN apk add --no-cache neovim screen

