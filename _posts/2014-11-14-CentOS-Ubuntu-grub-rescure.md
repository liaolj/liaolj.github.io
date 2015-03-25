---
layout: post
title: "CentOS7 Ubuntu14.04 grub 修复"
description: "grub修复"
category: linux
tags: [linux, grub]
notebook: A01_工作笔记
---
{% include JB/setup %}




### CentOS版本

因为CentOS现在采用的是grub2

#### 1.1 用u盘启动CentOS livecd 做如下操作

我之前安装的CentOS 在/dev/sda7

```python
mount /dev/sda7 /mnt
```

```python
sudo grub2-install --boot-directory=/mnt/boot /dev/sda
```

#### grub.cfg rebuild

#### 1.2 支持NTFS格式相关软件安装

[ntfs-3g-2013.1.13-5.el7.x86_64.rpm](ftp://ftp.sunet.se/pub/Linux/distributions/fedora/epel/7/x86_64/n/ntfsprogs-2013.1.13-5.el7.x86_64.rpm)
 
[ntfsprogs-2013.1.13-5.el7.x86_64.rpm](ftp://ftp.sunet.se/pub/Linux/distributions/fedora/epel/7/x86_64/n/ntfs-3g-2013.1.13-5.el7.x86_64.rpm)





### Ubuntu版本

#### 2.1 grub reinstall

用u盘启动CentOS livecd 做如下操作

我之前安装的CentOS 在/dev/sda7

```python
mount /dev/sda7 /mnt
```

 
```python
sudo grub-install --boot-directory=/mnt/boot /dev/sda
```


2.2 grub.cfg rebuild

```python
sudo update-grub
```
