---
layout: post
title: "安装P12文件"
description: "如何使用命令行安装P12文件"
category: 技术
tags: [OS X, P12, shell]
excerpt: "安装到当前login keychain中："

---
{% include JB/setup %}

文章来源：[stackoverflow](http://stackoverflow.com/questions/7485806/install-p12-or-cer-in-console-macos)

安装到当前login keychain中：

```
security unlock-keychain -p KeychainPassword login.keychain
security import FileName -P Password -k login.keychain
```

文章举例：

```
security create-keychain -p password bobbins.keychain
security add-certificates ./MyCertificate.cer

security unlock-keychain -p password bobbins.keychain
security import ./MyPrivateKey.p12 -k bobbins.keychain -P privateKeyPassword
```
