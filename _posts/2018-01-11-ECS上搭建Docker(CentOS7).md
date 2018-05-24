---
layout:     post
title:      ECS上搭建Docker(CentOS7)
subtitle:   云服务器安装docker,适用于centos7系统
date:       2018-01-11
author:     毒药
header-img: img/post-bg-re-vs-ng2.jpg
catalog: true
tags:
    - Docker
    - 云服务器
---


**1.安装docker**
----------

备注：Docker要求64位的系统且内核版本至少为3.10

 1. 添加yum源。
	

```
# yum install epel-release –y
# yum clean all
# yum list
```
 2. 安装并运行Docker
	

```
# yum install docker-io –y
# systemctl start docker
```

 3. 检查安装结果

```
# docker info
```
出现如下信息则表示安装成功,这段是结尾部分，前面还有很多

```
Security Options: seccomp
Kernel Version: 3.10.0-514.26.2.el7.x86_64
Operating System: CentOS Linux 7 (Core)
OSType: linux
Architecture: x86_64
Number of Docker Hooks: 3
CPUs: 1
Total Memory: 992.6 MiB
Name: iZuf6eptz3hom3dsj7b8xwZ
ID: LVZH:F4KG:WLF7:H43O:CHRT:PTME:4ES4:WHZV:O5Z5:ETJL:UI6Q:Q3DF
Docker Root Dir: /var/lib/docker
Debug Mode (client): false
Debug Mode (server): false
Registry: https://index.docker.io/v1/
Insecure Registries:
 127.0.0.0/8
Registries: docker.io (secure)
```

Docker基本用法
==========
1.Docker守护进程管理

```
# systemctl start docker     #运行Docker守护进程
# systemctl stop docker      #停止Docker守护进程
# systemctl restart docker   #重启Docker守护进程
```
2.查看已有的docker镜像

```
# docker images
```
先写这么多，后面再补充