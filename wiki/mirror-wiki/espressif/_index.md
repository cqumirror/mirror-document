---
title: "Espressif 镜像使用帮助"
draft: false
weight: 2
filepath: '/wiki/mirror-wiki/espressif/_index'
---

## 地址

https://mirrors.cqu.edu.cn/espressif

## 说明

乐鑫科技（Espressif）是一家全球领先的无晶圆厂半导体公司，其ESP等系列产品应用广泛，备受好评。

本仓库收录部分乐鑫开源项目。

{{% notice warning %}}
本同步仓库处于试运行期间，如有使用问题请及时反馈。
{{% /notice %}}

## 收录仓库

请查看 https://mirrors.cqu.edu.cn/git/espressif/ 以获取最新的仓库列表。

{{% notice note %}}
由于 Espressif 项目较多，且更新频繁，因此我们会根据用户需求和项目的重要性来选择性地收录仓库。如果您有特定的仓库需求，请及时反馈。
{{% /notice %}}

## 使用说明

### 首次拉取

首次拉取时，建议使用镜像站提供的[同步脚本库](https://mirrors.cqu.edu.cn/git/espressif/scripts/)，将自动递归克隆并处理子模块的URL，以便全程使用镜像站进行拉取。

以 esp-idf 仓库为例，使用以下命令：

```bash
bash <(curl -s https://mirrors.cqu.edu.cn/git/espressif/scripts/esp-idf.sh)
```

### 仓库更新

如使用同步脚本库进行首次拉取，则所有仓库的远程URL已经被替换为镜像站地址， 后续更新时，直接使用 `git pull` 或其他拉取命令，无需额外操作。

## 相关链接

{{% notice link %}}
官方主页[https://www.espressif.com](https://www.espressif.com)
{{% /notice %}}


{{% notice link %}}
GitHub 存储库[https://github.com/espressif](https://github.com/espressif)
{{% /notice %}}


