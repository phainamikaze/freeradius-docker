FROM alpine:3.6
MAINTAINER Witsanu Booonmakam <phai.namikaze@gmail.com>

WORKDIR /projects

RUN apk update && apk upgrade && \
    apk add --update freeradius freeradius-sqlite freeradius-radclient sqlite freeradius-rest && \
    chgrp radius  /usr/sbin/radiusd && chmod g+rwx /usr/sbin/radiusd && \
    rm /var/cache/apk/*

EXPOSE \
    1812/udp \
    1813/udp 

CMD ["radiusd","-xx","-f"]