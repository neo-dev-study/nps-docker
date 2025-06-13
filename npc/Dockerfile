FROM alpine:3.22

LABEL Name="nps-client"
LABEL Version="1.0.0"
LABEL maintainer="asuma"
LABEL description="NPS Client image based on alpine"


ARG TARGETOS
ARG TARGETARCH
ARG TARGETVARIANT

ARG FILE_URL=${TARGETOS}_${TARGETARCH}${TARGETVARIANT}_client.tar.gz

RUN apk update \
    && apk add -U tzdata \
    && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

COPY res/${FILE_URL} /var/tmp/

RUN cd /var/tmp/ \
    && mkdir npc \
    && tar -zxvf ${FILE_URL} -C npc \
    && cd npc \
    && mkdir /etc/npc \
    && cp -r ./conf /etc/npc/ \
    && ./npc install \
    && cd ../ \
    && rm -rf npc/ \
    && rm ${FILE_URL} \
    && rm /usr/bin/npc-update

CMD ["npc", "-config=/etc/npc/conf/npc.conf"]