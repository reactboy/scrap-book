---
title: command line navigations
date: 2022-01-04
categories: [command-line]
tags: []
author: eastasian
---
***
navigating
***
***
Root Directory
- The starting point for file syste.
- usually known as root, buy its actual name is "/".
- shorthand for the root directory is "/".

***
Hoom Directory
- /home contains a home folder for each user on the system.
- shorthand fot the home directory is "~".

***
pwd
- stands for "print working directory"
- 現在の作業中ディレクトリを表示する。
```
> pwd
/Users/ja
```

***
ls
- stands for "list".
- ディレクトリ内のフォルダとファイルを表示する。
- -l 詳細表示用のオプション
- -a 隠しフォルダ、ファイルの表示用オプション。
```
> ls
作業中ディレクトリのコンテンツ一覧の表示
> ls ディレクトリ名
指定ディレクトリ名のコンテンツ一覧の表示
```

***
cd
- stands for "change directory"
- 指定のディレクトリに移動する。
- "." means current directory.
- ".." means parent directory.
```
> cd ディレクトリ名
```

***
bin directory
- binary programsが格納されているディレクトリ

***
etc directory
- configurations filesが格納されているディレクトリ

***
var directory

***
log directory

***
root direcotry
- different from /.
- directory contains super user.

***
***
creating
***
***
touch
- a command to make a file or multiple files.
```
> touch ファイル名
```

***
file
- a command to display type of a file or files.
```
> file ファイル名
```

***
mkdir
- a command to make a directory or multiple directoies.
```
> mkdir ディレクトリ名
```

***
nano
- a simple text editor built in terminal.
```
> nano ファイル名
```

***
***
deleting, moving & copying.
***
***
rm
- rm stands for remove.
- a command to remove file from machine.
- -r or -d オプションでディレクトリを削除。
- -d オプションは空のディレクトリのみを削除ができる。
```
> rm ファイル名
> rm -r ディレクトリ名
```

***
mv
- mv stands for move.
- a command to move files or directories to another directory.
- 指定方法によってはファイル名/ディレクトリ名の変更できる。
```
> mv ファイル名 or ディレクトリ名 移動先ディレクトリ名
```

***
cp
- cp stands for copy,
- a command to copy files or directories to another directory
- ディレクトリのコピーは-rオプションの指定が必要。
```
> cp ファイル名 or ディレクトリ名 コピー先ディレクトリ
```

***
***
shortcuts
***
***
ctrl-l : clear
ctrl-a : jump to begininng of the line.
ctrl-e : jump to end of the line.
opt-right: jump word next
opt-left: jump word forward

***
history
- 今まで実行したコマンドを一覧表示する。
- 表示されたコマンドは!idで最実行できる。
    - idは一覧表示した際に合わせて表示される。
-     
```
> history
1000 ls
> !1000
```