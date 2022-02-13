---
title: drf installation
date: 2022-02-13
categories: [django, drf]
tags: []
author: eastasian
---

# Django Rest Frameworkの設定
- pipでDRFをインストールする
- djangoのsettings.pyを編集する

## pipでDRFをインストールする
requirements.txtに以下を追記する
```
djangorestframework == 3.13.1
```
>バージョンは必要なものを指定する

pipコマンドでrequirements.txtに記述されたパッケージをインストールする
```
pip install -r requirements.txt
```

## djangoのsettings.pyを編集する
djangoのsettings.pyの`INSTALLED_APPS`に`'rest_famework'`を追記する
```
INSTALLED_APPS = {
	'rest_framework'
}
```
上記手順でDRFを最小構成で使用できるようになる。

[DRF installation](https://www.django-rest-framework.org/#installation)