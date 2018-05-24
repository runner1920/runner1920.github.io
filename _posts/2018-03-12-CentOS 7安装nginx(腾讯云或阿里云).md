---
layout:     post
title:      云服务器安装nginx
subtitle:   centos7安装nginx详细步骤
date:       2018-03-12
author:     毒药
header-img: img/post-bg-re-vs-ng2.jpg
catalog: true
tags:
    - 云服务器
---

 1. 下载对应当前系统版本的nginx包(package)
```
wget  http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm
```
下载的文件名为:nginx-release-centos-7-0.el7.ngx.noarch.rpm
 2. 建立nginx的yum仓库
	  `rpm -ivh nginx-release-centos-7-0.el7.ngx.noarch.rpm`
 3. 下载并安装nginx
	

```
yum install nginx
```

 4. 启动nginx服务
	 

```
systemctl start nginx
```

 5. nginx配置文件
	  默认的配置文件在 /etc/nginx 路径下，使用该配置已经可以正确地运行nginx；如需要自定义，修改其下的 nginx.conf 等文件重启即可.
	  重启命令`systemctl restart nginx`
 6. 测试结果
 在浏览器地址栏中输入部署nginx环境的机器的IP，如果一切正常，应该能看到如下字样的内容。
 ![这里写图片描述](https://img-blog.csdn.net/20180322164417229?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3J1bm5lcjE5MjA=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
 安装完成，样式有点乱...