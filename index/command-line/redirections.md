---
title: command line redirections
date: 2022-01-09
categories: [command-line]
tags: []
author: eastasian
---
***
redirections
***
***
redirection outputs
- コマンドの出力先を変更する。
- デフォルトの出力先はターミナル。
- `>`は`1>`のショートハンド。
```
> コマンド名 > 出力先
> ls > output.txt
```

***
append outputs
- コマンドの出力を追記する。
```
> コマンド名 >> 追記先
```

***
redirection input
- コマンドにデータを渡す記法。
```
> cat < input.txt
> cat < input.txt > output.txt
> sort < sort.txt > sorted.txt
```

***
redirection error
- コマンド実行した際にエラーになった場合の出力先を変更する。
- デフォルトはターミナル。
- `2>>`で追記になる
```
> コマンド名 2> errorlog.txt
> コマンド名 2>> errorlog.txt
```

***
piping
- コマンドの結果を次のコマンドの引数として伝搬させる機能
```
> コマンド1 | コマンド2
```

***
