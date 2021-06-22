##1.跳转到指定行号
首先在normal模式下,100gg，或者 100 + shift + g(100G),意思就是跳到100行
##2.快速移动到行尾或者最后一行
第一行：gg。尾行：shift + g(G) .   行首:^(shift+6).行尾:$(shift+4)
##3.查找替换
会在全局范围(%)查找foo并替换为bar，所有出现都会被替换（g）
```shell
:%s/foo/bar/g
```
##4.查看行号
临时查看
```shell
:set number
:set nu
```
永久查看 最后一行输入 :set number
```shell
vim ~/.vimrc
```
##5.删除包含特定字符串的行
```shell
:g/str/d
```

##6.添加
###6.1 在每行行首添加相同的内容
```shell
:%s/^/内容
```
###6.2 在每行行尾添加相同的内容
```shell
:%s/$/内容
```
