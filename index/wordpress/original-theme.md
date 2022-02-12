---
title: wp original theme setup
date: 2022-02-12
categories: [wp]
tags: []
author: eastasian
---
# WPオリジナルテーマ
- wp-content/themesにオリジナルテーマ用フォルダを作成する。
- style.cssの設定をする。



## wp-content/themesにオリジナルテーマ用フォルダを作成する

以下の構造のフォルダをwp-content/themesに配置する。

```
wpのthemeフォルダ構造

/

├── editor-style.css
│
├── functions.php
│
├── index.php
│
├── screenshot.jpg/png/gif
│
└── style.css
```

***
## style.cssの設定
style.cssに以下の記述をすることでwp管理画面上でテーマとして認識されるようになる。

```
@charset "UTF-8";
/*
Theme Name:
author:
Description:
Version:
*/

```
上記は最低限のものでこれ以外の情報も設定できる。[ref](https://developer.wordpress.org/themes/basics/main-stylesheet-style-css/#example)
