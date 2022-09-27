FROM alpine:latest
MAINTAINER asuma

RUN apk update \
    && apk add -U tzdata \
    && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

COPY res/linux_amd64_server.tar.gz /var/tmp/

RUN cd /var/tmp/ \
    && mkdir nps \
    && tar -zxvf linux_amd64_server.tar.gz -C nps \
    && cd nps \
    && ./nps install \
    && cd ../ \
    && rm -rf nps/ \
    && rm linux_amd64_server.tar.gz \
    && rm /usr/bin/nps-update

CMD ["nps"]