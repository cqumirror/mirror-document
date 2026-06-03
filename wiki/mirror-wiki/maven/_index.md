---
title: "Maven 反向代理使用帮助"
draft: false
weight: 2
filepath: '/wiki/mirror-wiki/maven/_index'
---

## 地址

https://mirrors.cqu.edu.cn/maven

## 说明

Maven 是一个流行的 Java 项目管理和构建工具，广泛用于 Java 项目的依赖管理和构建过程。

本站提供 Maven Central、Gradle 以及其他一些常用的 Maven 仓库的反向代理服务。



## 使用说明

### 反向代理说明


| 名称 | 镜像地址 | 源地址 | 许可证     |
|------|----------|----------|---------|
| Maven 中央仓库 | `/maven/` | `https://repo.maven.apache.org/maven2/` | -       |
| Gradle 插件仓库 | `/maven/gradle/` | `https://plugins.gradle.org/m2/` | -       |
| SpigotMC 仓库 | `/maven/spigotmc/` | `https://repo.codemc.org/repository/nms/` | LGPL3   |
| PaperMC 仓库 | `/maven/papermc/` | `https://repo.papermc.io/repository/maven-public/` | GPL3    |
| SpongeMC 仓库 | `/maven/spongemc/` | `https://repo.spongepowered.org/repository/maven-public/` | MIT     |
| FabricMC 仓库 | `/maven/fabricmc/` | `https://maven.fabricmc.net/` | Apache2 |
| MinecraftForge 仓库 | `/maven/minecraftforge/` | `https://files.minecraftforge.net/maven/` | LGPL2.1 |
| NeoForged 仓库 | `/maven/neoforgemc/` | `https://maven.neoforged.net/releases/` | LGPL2.1 |

### Maven 配置
以 Maven 中央仓库为例，以下是一个示例配置：

#### 全局配置

- linux 用户在终端中输入以下命令:
```bash
mkdir ~/.m2
vim ~/.m2/settings.xml
```
- windows 用户在 powershell (或者pwsh中) 输入以下命令：
```powershell
mkdir ~/.m2
cd ~/.m2
notepad settings.xml
```

如果打开的文件为空，粘贴以下内容：
```xml
<?xml version="1.0" encoding="UTF-8"?>
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 http://maven.apache.org/xsd/settings-1.0.0.xsd">
    <mirrors>
       <mirror>
            <id>cqu_mirror</id>
            <mirrorOf>*</mirrorOf>
            <url>https://mirrors.cqu.edu.cn/maven/</url>
        </mirror>
    </mirrors>
</settings>
```
如果已经有内容，则在 mirrors 节点加入子节点 (对于 mirrorOf 值相同的节点，只有首个子节点生效)：
```xml
<mirror>
    <id>cqu_mirror</id>
    <mirrorOf>*</mirrorOf>
    <url>https://mirrors.cqu.edu.cn/maven/</url>
</mirror>
```
#### 项目配置
如果只在某个项目中使用，则在项目的 `pom.xml` 中配置：
```xml
<project>
    ......[其他配置]
    
    <repositories>
        <repository>
            <id>cqu</id>
            <url>https://mirrors.cqu.edu.cn/maven/</url>
            <releases>
                <enabled>true</enabled>
            </releases>
            <snapshots>
                <enabled>false</enabled>
            </snapshots>
        </repository>
    </repositories>
</project>
```

## 相关链接

{{% notice link %}}
官方主页[https://www.maven.org/](https://www.maven.org/)
{{% /notice %}}

{{% notice link %}}
南京大学 eScience 中心 Maven 帮助文档[https://doc.nju.edu.cn/books/e1654/page/maven](https://doc.nju.edu.cn/books/e1654/page/maven)
{{% /notice %}}
