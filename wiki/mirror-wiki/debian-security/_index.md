---
title: "Debian 安全更新使用帮助"
draft: false
weight: 2
filepath: '/wiki/mirror-wiki/debian-security/_index'
---

## 地址

https://mirrors.cqu.edu.cn/debian-security

## 说明

Debian 安全更新仓库

## 收录架构

Debian 支持的部分架构，如 amd64, arm64, armhf, i386, riscv64, 以及 source code。

## 收录版本

- oldoldstable (bullseye)
- oldstable (bookworm)
- stable (trixie)
- testing (forky)

## 使用说明

{{% notice warn %}}
**一般情况下，用户获取安全更新应该直接使用`http://security.debian.org/debian-security`而非指定别的镜像站。**<br />
Debian 的[安全更新源](security.debian.org)是为了使安全更新**尽快可用**。<br />
使用非官方镜像站会让此增加不必要的麻烦，尤其是这些镜像站没有及时更新时。
详见 <https://www.debian.org/security/>。
{{% /notice %}}


默认情况下，以下命令可以将默认软件源（`security.debian.org/debian-security`）替换为重庆大学镜像站（`mirrors.cqu.edu.cn/debian-security`）并启用安全更新：
```bash
sudo sed -i 's|#*deb http://security.debian.org|deb https://mirrors.cqu.edu.cn|' /etc/apt/sources.list
```

如果出现“USERNAME 不在 sudoers 文件中。此事将被报告”或“USERNAME is not in the sudoers file.  This incident will be reported.”
可以使用

```bash
su -c "sed -i 's|#*deb http://security.debian.org|deb https://mirrors.cqu.edu.cn|' /etc/apt/sources.list"
```

来完成这一操作。

但我们更推荐更安全的做法——`sudo`。[如何配置`sudo`](/wiki/mirror-wiki/debian/sudo)。

另外，您亦可手动编辑`/etc/apt/sources.list`。

### DEB822

DEB822 是新版的 Debian 软件仓库配置格式。推荐 Debian 12 (Bookworm) 及以上版本使用新版格式。

[参考 DEB822 配置](/wiki/mirror-wiki/debian/deb822)
