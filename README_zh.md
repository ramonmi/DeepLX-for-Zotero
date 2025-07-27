# DeepLX-for-Zotero
Documentation: Using the DeepLX(API) service with Translate for Zotero in Zotero.

[English](README.md) | 中文

# API DeepLX - LINUX DO

**https://api.deeplx.org**

- 为防止滥用，该DeepLX API已添加 LINUX DO Connect 认证，需要注册登录[LINUX DO](https://linux.do/)获取`<api-key>`，详见https://linux.do/t/topic/111737

**在 Zotero 中配置**

- 打开Zotero-设置-翻译，选择服务中的DeepLX(API)📍翻译服务，点击 **配置**，将你的接口地址填入*接口*并保存即可。
  - 最新的接口地址为：`https://api.deeplx.org/<api-key>/translate`，其中`<api-key>`需替换为你自己的`DeepLX Api Key`字符串

# DeepL Docker

## 简介

由于各种原因，在国内注册 DeepL 的免费计划都十分困难。利用DeepL Docker可让用户在不注册账号的前提下，使用 DeepL 作为翻译服务。

[zu1k](https://github.com/zu1k) 通过逆向 DeepL 客户端使用的协议，实现免费的 DeepL API。

## 具体步骤

**1. 安装 Docker**

参考： [Docker 官网](https://www.docker.com/)

**2. 拉取镜像**

在终端中执行：

```Shell
docker pull kanikig/deepl-bk
```

由于原作者 zu1k 已删除镜像，因而使用 [KANIKIG](https://github.com/KANIKIG) 的备份。

**3. 部署 DeepL 服务**

Mac(Intel)和Windows：

```Shell
docker run -itd -p 8080:80 kanikig/deepl-bk 
```

Mac(M1/M2)：

```Shell
docker run --platform linux/amd64 -p 8080:80 -itd kanikig/deepl-bk
```

其中，`8080`是服务运行的端口，可以修改为其他数值。

**4. 在 Zotero 中配置**

- 打开Zotero-设置-翻译，选择服务中的DeepLX(API)📍翻译服务，点击 **配置**，将网址填入*接口*并保存即可。
  - 如果按照上文进行配置，则应填写：`http://127.0.0.1:8080/translate`，如修改了服务运行端口，则需将`8080`替换为修改后的端口号

## 参考链接

如果访问速度慢，可参考 [Mac 翻译软件Bob，使用免费DeepL API](https://zhuanlan.zhihu.com/p/484946276) 设置代理。

其他参考链接：

[zu1k的项目](https://zu1k.com/projects/#deepl-free-api)

[zu1k/deepl docker](https://hub.docker.com/r/zu1k/deepl)

[kanikig/deepl-bk docker](https://hub.docker.com/r/kanikig/deepl-bk)

## 致谢

[KyleChoy/zotero-pdf-translate](https://github.com/KyleChoy/zotero-pdf-translate)