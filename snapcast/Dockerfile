ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Copy data for add-on
COPY rootfs /

RUN printf "@edge http://dl-cdn.alpinelinux.org/alpine/edge/main\n@edge http://dl-cdn.alpinelinux.org/alpine/edge/community\n@testing http://dl-cdn.alpinelinux.org/alpine/edge/testing\n" >> /etc/apk/repositories
RUN apk update
# Align C++ runtime with edge packages to avoid GLIBCXX symbol mismatch
RUN apk add --no-cache libstdc++@edge libgcc@edge
RUN apk add --no-cache \
    snapcast@edge snapcast-server@edge snapcast-client@edge \
    librespot@testing \
    alsa-plugins-pulse
#RUN apk add --no-cache neovim screen

