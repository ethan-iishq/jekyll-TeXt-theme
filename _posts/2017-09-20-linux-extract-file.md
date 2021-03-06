---
layout: post
title: linux下解压tar.xz文件的命令
key: 20160920
tags: linux
---

### 1. xz压缩文件方法或命令

`$xz -z 要压缩的文件`

> 如果要保留被压缩的文件加上参数 -k ，如果要设置压缩率加入参数 -0 到 -9调节压缩率。如果不设置，默认压缩等级是6.

### 2. xz解压文件方法或命令

`$xz -d 要解压的文件`

> 同样使用 -k 参数来保留被解压缩的文件。

### 3. 创建或解压tar.xz文件的方法

> 习惯了 tar czvf 或 tar xzvf 的人可能碰到 tar.xz也会想用单一命令搞定解压或压缩。其实不行 tar里面没有征对xz格式的参数比如 z是针对 gzip，j是针对 bzip2。

创建tar.xz文件：只要先 `$tar cvf xxx.tar xxx/` 这样创建xxx.tar文件先，然后使用 `$xz -z xxx.tar` 来将 xxx.tar压缩成为 xxx.tar.xz

解压tar.xz文件：先 `$xz -d xxx.tar.xz` 将 xxx.tar.xz解压成 xxx.tar 然后，再用 `$tar xvf xxx.tar`来解包。