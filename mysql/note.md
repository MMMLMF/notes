### mysql中添加数据时,报错(incorrect string value:'\xf0\x9f ) 字符转换不正确

1.在mysql的安装目录下找到my.ini,作如下修改：
```
[mysqld]

character-set-server=utf8mb4

[mysql]

default-character-set=utf8mb4
```
修改后重启Mysql

2. 将已经建好的表也转换成utf8mb4

命令：
```
alter table TABLE_NAME convert to character set utf8mb4 collate utf8mb4_bin; 
```
（将TABLE_NAME替换成你的表名）


