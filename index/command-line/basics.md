---
title: command line basics
date: 2022-01-03
categories: [command-line]
tags: []
author: eastasian
---

***
date
日付を表示
ex)
```
> date
Mon Jan  3 20:15:05 JST 2022
```

***
ncal
カレンダー(縦)を表示
```
> ncal
    January 2022
Mo     3 10 17 24 31
Tu     4 11 18 25
We     5 12 19 26
Th     6 13 20 27
Fr     7 14 21 28
Sa  1  8 15 22 29
Su  2  9 16 23 30
```

***
cal
カレンダー(横)を表示
```
> cal
    January 2022
Su Mo Tu We Th Fr Sa
                   1
 2  3  4  5  6  7  8
 9 10 11 12 13 14 15
16 17 18 19 20 21 22
23 24 25 26 27 28 29
30 31
```

***
clear
ターミナルに表示されている内容を非表示にする

***
tips
ターミナルで⬆️を入力で直前に入力したコマンドを遡れる

***
basic command structure
```
> command -options arguments
```
command:
実行したいコマンド。

options:
実行したいコマンドのオプション。
-オプション名で指定する。(ショートフォーム)
--オプション名で指定する。(ロングフォーム)
スペース区切りで複数指定することができる。

arguments:
実行したいコマンドの引数。
引数を経由してコマンドの実行に必要な情報を指定できる。
スペース区切りで複数指定することができる。
パラメータとも呼ばれる。

***
echo
argumentsとして指定した文字列を出力する
```
> echo hello
hello
```

***
man
コマンドのマニュアルを表示する
```
> man コマンド名
```

***
type
コマンドのタイプを表示する
- executable program (/bin, /usr/bin or /usr/local/bin).
    - also known as compiled binary files.
- built in shell commands
- shell function
- alias
```
> type zsh
zsh is /bin/szh

> type echo
echo is a shell builtin
```

***
which
コマンドのディレクトリを表示する
```
> which /bin/zsh
/bin/zsh

> which echo
echo: shell built-in command
```

***
help
コマンドのマニュアルを表示する
manコマンドでマニュアルが表示されない場合はこっちを使用する
manコマンドではbuilt in shell commandのマニュアルが用意されていない場合がある
```
> help コマンド名
```

***
