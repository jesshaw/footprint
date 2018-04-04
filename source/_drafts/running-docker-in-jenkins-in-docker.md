---
title: 在docker中的jenkins如何运行兄弟docker
tags: docker, jenkins
categories: 
  - docker

thumbnail: /gallery/blue-water1.jpg
---
容器间的通信
<!-- more -->

docker不可避免的会跟CD和CI联系上，当使用docker搭建jenkins时。因为docker容器一般是独立部署，会把打包好的数据，在兄弟容器启动。本文讲述如何在jenkins容器中跟兄弟容器通信，从而实现一键发布的功能。其关键就是docker sock的映射实现容器间的通信。

## 通过Dockerfile创建一个jenkins镜像

```bash
FROM jenkins:2.60.3

USER root
RUN apt-get update \
      && apt-get install -y sudo libltdl7 \
      && rm -rf /var/lib/apt/lists/*
RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers
 
USER jenkins
COPY plugins.txt /usr/share/jenkins/plugins.txt
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt
```

把jenkins添加到sudoer用户组，给其制制授权避免jenkins用户执行不了docker的问题

新建plugins.txt，增加需要的插件
```bash
$ cat plugins.txt
scm-api:latest
git-client:latest
git:latest
greenballs:latest
```

## 接下来构建镜像并运行容器，并映射Docker socket和binary。

```bash
$ docker build -t myjenk .
...
Successfully built 12dafdsafsf1213
$ docker run -d -v /var/run/docker.sock:/var/run/docker.sock \
                -v $(which docker):/usr/bin/docker -p 8080:8080 myjenk

```
这样jenkins就启动了，然后不需要安装其他任何插件。

## 按以下步骤创建一个项目

* 在浏览器中打开Jenkins并创建一个新的项目。 Open the Jenkins home page in a browser and click the “create new jobs” link.
* 选择 “Freestyle project” ，输了一个名为“docker-test”的名称，保存。
* 在配置页上点击“Add build step” 添加 “Execute shell”。
* 在命令中输入 “sudo docker run hello-world”。
* 保存并立即构建。

运行成功则说明容器间通信成功。

[DooD](http://container-solutions.com/running-docker-in-jenkins-in-docker/)
[libltdl7问题](https://www.cnblogs.com/leolztang/p/6934694.html)