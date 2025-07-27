# DeepLX-for-Zotero
Documentation: Using the DeepLX(API) service with Translate for Zotero in Zotero.

English | [中文](README_zh.md)

# API DeepLX - LINUX DO

**https://api.deeplx.org**

- To prevent abuse, the DeepLX API has added LINUX DO Connect authentication and requires registration and login on [LINUX DO](https://linux.do/) to obtain `<API key>`, see https://linux.do/t/topic/111737 for details.

**Configure in Zotero**

- Zotero -> Settings -> Translate, select translate service DeepLX(API)📍in the Service section, click **Config**, enter URL in the *EndPoint* inputbox and save it.
  - Latest URL: `https://api.deeplx.org/<api-key>/translate`. Replace `<api-key>` with your own `DeepLX Api Key` string.
# DeepL Docker

## Introduction

Using DeepL Docker allows users who have troubles creating accounts to use DeepL service without registering for an account.

By reverse engineering DeepL client, [zu1k](https://github.com/zu1k) provides access to DeepL without creating accounts.

## How-to

**1. Install Docker**

See [Docker Website](https://www.docker.com/).

**2. Pull Image**

Run in terminal:

```Shell
docker pull kanikig/deepl-bk
```

[zu1k](https://github.com/zu1k) has deleted the image, therefore using a backup from [KANIKIG](https://github.com/KANIKIG).

**3. Deploy DeepL Service**

Mac(Intel) and Windows:

```Shell
docker run -itd -p 8080:80 kanikig/deepl-bk 
```

Mac(M1/M2):

```Shell
docker run --platform linux/amd64 -p 8080:80 -itd kanikig/deepl-bk
```

`8080` is the port where the service will be running on. It can be modified to any other available port.

**4. Configure in Zotero**

- Zotero -> Settings -> Translate, select translate service DeepLX(API)📍in the Service section, click **Config**, enter URL in the *EndPoint* inputbox and save it。
  - If you follow as above, the URL should be: `http://127.0.0.1:8080/translate`; If you change the service running port, you need to replace `8080` with the modified port number.

## Reference

If the access speed is slow, please refer to [Mac 翻译软件Bob，使用免费DeepL API](https://zhuanlan.zhihu.com/p/484946276) to set up a proxy.

[zu1k'projects](https://zu1k.com/projects/#deepl-free-api)

[zu1k/deepl docker](https://hub.docker.com/r/zu1k/deepl)

[kanikig/deepl-bk docker](https://hub.docker.com/r/kanikig/deepl-bk)

## Acknowledgement

[KyleChoy/zotero-pdf-translate](https://github.com/KyleChoy/zotero-pdf-translate)