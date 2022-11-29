FROM ghcr.io/linuxserver/baseimage-alpine:3.16

WORKDIR /config

RUN \
  echo "**** install build packages ****" && \
  apk add --no-cache --virtual=build-dependencies \
    tar \
    xmlstarlet && \
  echo "**** install runtime packages ****" && \
  apk add --no-cache \
    go && \
    go get github.com/cooper/quiki && \ 
    cp quiki.conf.example quiki.conf

COPY /root/ /

EXPOSE 80 443
VOLUME /config
