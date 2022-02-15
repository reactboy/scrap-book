---
title: wp dev environment setup
date: 2022-02-14
categories: [wp]
tags: []
author: eastasian
---
# wp開発環境の構築
- docker-compose.ymlの作成

## docker-compose.ymlの作成
ymlファイルを作成する。
```
version: '3'

services:

	db:
	
		image: mariadb:10.2
		
		volumes:
		
		- ./db_data:/var/lib/mysql
		
		restart: always
		
		environment:
		
			MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD}
			
			MYSQL_DATABASE: ${MYSQL_DATABASE}
			
			MYSQL_USER: ${MYSQL_USER}
			
			MYSQL_PASSWORD: ${MYSQL_PASSWORD}
	
	wordpress:
	
		image: wordpress:latest
		
		ports:
		
			- "8000:80"
		
		restart: always
		
		environment:
		
			WORDPRESS_DB_HOST: db:3306
			
			WORDPRESS_DB_USER: ${MYSQL_USER}
			
			WORDPRESS_DB_PASSWORD: ${MYSQL_PASSWORD}
		
		volumes:
		
			- ./wp-content:/var/www/html/wp-content
		
		depends_on:
		
			- db

```

以下のコマンドでdocker環境を実行する。
```
docker compose up
```

***
