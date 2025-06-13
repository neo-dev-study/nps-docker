# NPS

![](https://img.shields.io/github/stars/ehang-io/nps.svg) ![](https://img.shields.io/github/forks/ehang-io/nps.svg)
[![Gitter](https://badges.gitter.im/cnlh-nps/community.svg)](https://gitter.im/cnlh-nps/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

[官方文档](https://ehang-io.github.io/nps/#/example)

nps 是一款轻量级、高性能、功能强大的**内网穿透**代理服务器。目前支持**tcp、udp 流量转发**，可支持任何**tcp、udp**上层协议（访问内网网站、本地支付接口调试、ssh 访问、远程桌面，内网 dns 解析等等……），此外还**支持内网 http 代理、内网 socks5 代理**、**p2p 等**，并带有功能强大的 web 管理端。

## 开始

### 服务端启动（nps）

#### Docker

```
docker run -d --name nps --net=host iasuma/nps
```

#### Docker Compose

```
version: "3"
services:
  nps:
    image: iasuma/nps
    container_name: nps
    volumes:
      - ./conf:/etc/nps/conf:rw
    #ports:
    #  - "8080:8080"
    #  - "8024:8024"
    #  - "80:80"
    #  - "443:443"
    network_mode："host"
    restart: always
```

#### Config Download

Download：[服务端配置](https://github.com/iAsuma/nps-docker/tree/master/nps/conf)

### 客户端启动（npc）

#### Docker

```
docker run -d --name npc --net=host iasuma/npc
```

#### Docker Compose

```
version: "3"
services:
  nps:
    image: iasuma/npc
    container_name: npc
    volumes:
      - ./conf:/etc/npc/conf:rw
    restart: always
    network_mode: host
```

#### Config Download

Download：[客户端配置](https://github.com/iAsuma/nps-docker/tree/master/npc/conf)

### linux_amd64_server.tar.gz 在下面连接下载

https://github.com/ehang-io/nps/releases
