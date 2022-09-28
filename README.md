
# NPS
![](https://img.shields.io/github/stars/ehang-io/nps.svg)   ![](https://img.shields.io/github/forks/ehang-io/nps.svg)
[![Gitter](https://badges.gitter.im/cnlh-nps/community.svg)](https://gitter.im/cnlh-nps/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

[官方文档](https://ehang-io.github.io/nps/#/example)

nps是一款轻量级、高性能、功能强大的**内网穿透**代理服务器。目前支持**tcp、udp流量转发**，可支持任何**tcp、udp**上层协议（访问内网网站、本地支付接口调试、ssh访问、远程桌面，内网dns解析等等……），此外还**支持内网http代理、内网socks5代理**、**p2p等**，并带有功能强大的web管理端。


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

#### 配置下载
[服务端配置](https://github.com/iAsuma/nps-docker/tree/master/nps/conf)
