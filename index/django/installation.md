---
title: django installation
date: 2022-02-12
categories: [python, django]
tags: []
author: eastasian
---

# djangoのインストール

- venvでpythonの仮想環境の構築
- pipでdjangoをインストール
- djangoプロジェクトを作成する

## venvでpythonの仮想環境を構築
pythonがインストールされた状態でターミナルにて以下を実行する。
```
// 仮想環境の初期化
python -m venv {仮想環境名}

// 仮想環境のactivate
source {仮想環境名}/source/bin

// 仮想環境のdeactivate
deactivate
```
[venv]()

## pipでdjangoをインストール
venvがactivateされた状態でpipでdjangoをインストールする。
requirements.txtを作成し、以下を追記する。
```
Django == 3.2.12
```
>バージョンは任意 

requirements.txtがある状態で以下のpipコマンドを実行する。
```
pip install -r requirements.txt
```

requirements.txtを使用せず直接pipでインストールもできる。
```
pip install Django
```
>バージョンを指定しない場合は最新がインストールされる。

[django version](https://www.djangoproject.com/download/)
[django installation](https://docs.djangoproject.com/en/3.2/intro/install/)
[pip requirements.txt](https://note.nkmk.me/en/python-pip-install-requirements/)

## djangoプロジェクトの作成
djangoがインストールされた状態で以下を実行する。
```
django-admin startproject {プロジェクト名} {パス}
```
> 基本的にパスは`.` を指定してい今いるdir内にファイルを配置する。

以下のコマンドでdjangoを開始する。
```
python manage.py runserver
```

[localhost:8000](http://localhost:8000/)で表示が確認できる。
デフォルトでは8000でサーバがスタートする。