---
layout: post
title: "CentOS7 常用命令整理"
description: "CentOS7 升级之后常用命令更改整理"
category: linux
tags: [linux, centos]
---
{% include JB/setup %}

### 介绍
CentOS 7 已经切换到 systemd,之前用于启动、重启、停止各种服务的 service 仍然还能使用。同时，chkconfig 也改成了 systemctl 了。

[root@localhost ~]# service network restart

[root@localhost ~]# service httpd restart
Redirecting to /bin/systemctl restart  httpd.service

[root@localhost ~]# service sshd restart
Redirecting to /bin/systemctl restart  sshd.service
但是系统会自动重定向该指令到新的指令 /bin/systemctl 来执行，并给出提示。

是时候切换到新的指令格式了，直接使用 systemctl 吧。这个指令的意思就是 system contrl。下面是一些常用的例子：

启动服务：

systemctl start httpd
停止服务：

systemctl stop httpd
重启服务（先停止，后启动）：

systemctl restart httpd
重新加载（使用新的配置文件）：

systemctl reload httpd
显示服务状态：

systemctl status httpd
与此同时，之前用于设定系统启动时自动运行某服务的指令 chkconfig 也改了，还是用 systemctl。

chkconfig service on
systemctl enable httpd
chkconfig service off
systemctl disable httpd
检查服务状态的

chkconfig service
systemctl is-enabled httpd
列举出所有服务的指令，

chkconfig –list
systemctl list-unit-files --type=service
以前能指定服务 runlevel 的 –levels 也没有了。慢慢适应吧。©

