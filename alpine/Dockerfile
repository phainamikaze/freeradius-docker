FROM alpine:3.6
MAINTAINER Witsanu Booonmakam <phai.namikaze@gmail.com>

WORKDIR /projects

RUN apk update && apk upgrade && \
    apk add --update freeradius freeradius-sqlite freeradius-radclient sqlite openssl-dev freeradius-rest freeradius-python&& \
    chgrp radius  /usr/sbin/radiusd && chmod g+rwx /usr/sbin/radiusd && \
    rm /var/cache/apk/*

VOLUME \
    /opt/db/ \
    /etc/freeradius/certs

EXPOSE \
    1812/udp \
    1813 \
    18120

CMD ["radiusd","-xx","-f"]