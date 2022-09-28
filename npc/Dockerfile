FROM alpine:latest
MAINTAINER asuma

RUN apk update \
    && apk add -U tzdata \
    && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

COPY res/linux_amd64_client.tar.gz /var/tmp/

RUN cd /var/tmp/ \
    && mkdir npc \
    && tar -zxvf linux_amd64_client.tar.gz -C npc \
    && cd npc \
    && mkdir /etc/npc \
    && cp -r ./conf /etc/npc/ \
    && ./npc install \
    && cd ../ \
    && rm -rf npc/ \
    && rm linux_amd64_client.tar.gz \
    && rm /usr/bin/npc-update

CMD ["npc", "-config=/etc/npc/conf/npc.conf"]