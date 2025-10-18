ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Copy data for add-on
COPY rootfs /

RUN printf "@edge http://dl-cdn.alpinelinux.org/alpine/edge/main\n@edge http://dl-cdn.alpinelinux.org/alpine/edge/community\n@edge http://dl-cdn.alpinelinux.org/alpine/edge/testing\n" >> /etc/apk/repositories  
RUN apk update
RUN wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub
RUN wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.35-r1/glibc-2.35-r1.apk
RUN apk add glibc-2.35-r1.apk
RUN apk add --no-cache openrc
RUN apk add --no-cache snapcast@edge snapcast-server@edge snapcast-client@edge
RUN apk add --no-cache librespot@edge
RUN apk add --no-cache alsa-plugins-pulse
#RUN apk add --no-cache neovim screen

