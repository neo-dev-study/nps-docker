FROM alpine:3.22

LABEL Name="nps-server"
LABEL Version="1.0.0"
LABEL maintainer="asuma"
LABEL description="NPS Server image based on alpine"

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