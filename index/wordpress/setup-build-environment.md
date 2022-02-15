---
title: wp front environment setup
date: 2022-02-14
categories: [wp]
tags: []
author: eastasian
---

# wpのフロント環境の構築
- package.jsonの作成
- wp-scriptsのインストール
- wpでフロントのアセットの読み込みの設定

## package.jsonの作成
カスタムテーマのルートにて以下のコマンドでpackage.jsonの初期化をする。
```
npm init -y
```

## wp-scriptsのインストール
以下のコマンドで`wp-scripts`をdev dependenciesに追加する。
```
npm install @wordpress/scripts --save-dev
```
任意のwp-scriptsコマンドをnpm scriptsに設定する。
```
"scripts": {

	"build": "wp-scripts build",
	
	"check-engines": "wp-scripts check-engines",
	
	"check-licenses": "wp-scripts check-licenses",
	
	"format": "wp-scripts format",
	
	"lint:css": "wp-scripts lint-style",
	
	"lint:js": "wp-scripts lint-js",
	
	"lint:md:docs": "wp-scripts lint-md-docs",
	
	"lint:md:js": "wp-scripts lint-md-js",
	
	"lint:pkg-json": "wp-scripts lint-pkg-json",
	
	"packages-update": "wp-scripts packages-update",
	
	"plugin-zip": "wp-scripts plugin-zip",
	
	"start": "wp-scripts start",
	
	"start:hot": "wp-scripts start --hot",
	
	"test:e2e": "wp-scripts test-e2e",
	
	"test:unit": "wp-scripts test-unit-js"

},

```
[wp-scripts setup](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-scripts/#setup)
カスタムテーマのルートに以下の構造でフロントのアセット用のフォルダを作成する。
```
/

├── /src
│	├─ /style
│	│  └─ style.scss
│   └─ index.js
```
index.js内にてstyle.scssを読み込むことでjsコンパイル時にscssも合わせてコンパイルされるようになる。
```
import "./style/style.scss"
```

## wpでフロントのアセットの読み込みの設定
ビルドされたフロント関連のアセットをwpで読み込むようにする。
functions.phpに以下の記述を追加する。
```
function custom-theme_register_files() {

	wp_enqueue_style(
	
		'style',
		
		get_stylesheet_uri(),
		
		array(),
		
		filemtime(get_theme_file_path('style.css'))
	
	);
	
	wp_enqueue_style(
	
		'main-style',
		
		get_theme_file_uri('/build/style-index.css'),
		
		array(),
		
		filemtime(get_theme_file_path('/build/style-index.css'))
	
	);
	
	// maybe load before body tag end
	
	wp_enqueue_script(
		
		'main-js',
		
		get_theme_file_uri('/build/index.js'),
		
		array(),
		
		filemtime(get_theme_file_path('/build/index.js'))
	
	);

}

add_action('wp_enqueue_scripts', 'aidabluee_register_files');

```