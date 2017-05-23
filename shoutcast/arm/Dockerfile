#
# Dockerfile for shoutcast-arm
#

FROM armhf/debian:jessie

MAINTAINER EasyPi Software Foundation

WORKDIR /opt/shoutcast

RUN set -xe \
    && apt-get update \
    && apt-get install -y curl \
    && curl http://www.goldmusic.de/static/download/sc_serv2_armv6_rpi_07_31_2014.tar.gz | tar xz \
    && mkdir -p control logs \
    && apt-get purge --auto-remove -y curl \
    && rm -rf /var/lib/apt/lists/*

COPY sc_serv.conf .

EXPOSE 8000 8001

CMD ["./sc_serv", "sc_serv.conf"]
