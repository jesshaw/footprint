---
title: docker常用命令
tags: docker,docker命令
categories: 
  - docker

thumbnail: /gallery/blue-water9.jpg
---

收集平时常用的一些docker命令。
<!-- more -->

##### 拉取镜像
```bash
docker pull
```

##### 创建镜像
```bash
docker build
```

##### 列出镜像
```bash
docker imgaes
```

##### 运行容器
```bash
docker run
```

##### 列出容器
```bash
docker ps
docker ps -a
```

##### 删除容器
```bash
docker rm
```

##### 删除镜像
```bash
docker rmi
```

##### 在host和container之间拷贝文件
```bash
docker cp
```

##### 保存改动为新的镜像
```bash
docker commit 
```

##### 进行docker容器

```bash
docker exec -it [container id] bash
```




