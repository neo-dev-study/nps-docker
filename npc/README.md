
# NPS

nps是一款轻量级、高性能、功能强大的**内网穿透**代理服务器。目前支持**tcp、udp流量转发**，可支持任何**tcp、udp**上层协议（访问内网网站、本地支付接口调试、ssh访问、远程桌面，内网dns解析等等……），此外还**支持内网http代理、内网socks5代理**、**p2p等**，并带有功能强大的web管理端。

[官方文档](https://ehang-io.github.io/nps/#/use)

## 开始

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