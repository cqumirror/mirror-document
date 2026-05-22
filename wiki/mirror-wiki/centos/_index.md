---
title: "CentOS 镜像使用帮助"
draft: false
weight: 2
filepath: '/wiki/mirror-wiki/centos/_index'
---
{{% notice note %}}
因 CentOS 已终止支持，本镜像站 CentOS 仓库仅对校内用户提供服务，且仅提供 [7.9.2009](https://mirrors.cqu.edu.cn/centos/7.9.2009/) 版本的镜像服务。
{{% /notice %}}

## 地址

http://mirrors.cqu.edu.cn/CentOS

## 说明

CentOS 软件源

## 收录架构

- x86_64
- i386

## 收录版本

- CentOS 7.9.2009

## 使用说明

首先备份`CentOS-Base.repo`:


```bash
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
```

下载文件到指定目录：</br>

```bash
wget   -O   /etc/yum.repos.d/CentOS-Base.repo  http://mirrors.cqu.edu.cn/repo/centos/Centos-7.repo
```


{{% notice note %}}
有些情况下系统没有预装`wget`程序，请提前进行安装。
{{% /notice %}}


然后刷新 yum 缓存：

```bash
yum makecache
```

## 相关链接


{{% notice link %}}
官方主页：https://www.centos.org/
{{% /notice %}}


{{% notice link %}}
邮件列表：https://www.centos.org/modules/tinycontent/index.php?id=16
{{% /notice %}}


{{% notice link %}}
论坛：https://www.centos.org/modules/newbb/
{{% /notice %}}


{{% notice link %}}
文档：https://www.centos.org/docs/
{{% /notice %}}


{{% notice %}}
Wiki：https://wiki.centos.org/
{{% /notice %}}
