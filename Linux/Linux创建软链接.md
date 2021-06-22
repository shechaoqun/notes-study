##linux创建软链接
等于windows中创建快捷方式
```shell
ln -s /pwd /usr/local/bin/abc
```
删除软链接,abc 后不可以加/ 否则会删除源文件
```shell
rm /usr/local/bin/abc
```

查看是否有软链接
```shell
ll -al 
```