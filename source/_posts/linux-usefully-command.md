---
title: linux常用命令
tags: linux,linux
categories: 
  - linux
thumbnail: /gallery/blue-water9.jpg
---

收集平时常用的一些linux命令。
<!-- more -->

## ssh几个超时参数

### 客户端方案
Host *
    ServerAliveInterval 60

### 服务器方案
```bash
vim /etc/ssh/sshd_config
```

#ClientAliveInterval 0改为ClientAliveInterval 500     （每500秒往客户端发送会话请求，保持连接）

#ClientAliveCountMax 3      （去掉注释即可，3表示重连3次失败后，重启SSH会话）
```bash
systemctl restart sshd   #重启sshd服务
```


http://www.361way.com/ssh-autologout/4679.html

## 更改密码
```bash
$  passwd
```




