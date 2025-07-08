---
title: Docker简单上手
date: 2024-01-25
category: notes
---

**TLDR** 配置环境，写自己的docker，跑自己的app并且部署到云上


# 安装

Follow [docker doc](https://docs.docker.com/engine/install/ubuntu/) 安装 docker engine。

在ubuntu里启动 docker daemon

```bash
sudo dockerd
```

# 第一个docker run
```bash
sudo docker run hello-world
```

# build docker
过去一段时间的经验是,写个build_docker_image.sh的脚本build, tag和push到dockerhub上

# deploy docker
可以使用docker pull或者docker run的命令来用,不过在部署了k8s以后,可以配置好service和deployment yaml,直接使用kubectl apply来部署
