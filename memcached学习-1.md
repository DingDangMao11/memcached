# memcached
```
1.安装
sudo apt install memcached
2.启动
service memcached start
3.前台启动
/usr/bin/memcached -u memcache start
4.-d 表示后台启动
/usr/bin/memcached -u memcache -d start
5.登陆其它主机的memcached，启动命令
/usr/bin/memcached -l 0.0.0.0 -u memcache -d start
6.本机登录memcache
telnet 127.0.0.1 11211
```
#  通过python操作memcached
```
#encoding:utf-8

import memcache

#在连接之前，确认先启动memcached
mc = memcache.Client(["127.0.0.1:11211"],debug=True)
## 设置数据：
mc.set('username','abc',time=120)
mc.set_multi({'title':'钢铁是怎样练成的','content':'hello world'},time=120)
## 获取数据：
username = mc.get('username')
print(username)
```
```
get username
VALUE username 16 7
zhiliao
END
get username
VALUE username 16 3
abc
END
get title
VALUE title 16 24
钢铁是怎样练成的
END
get content
VALUE content 16 11
hello world
END
set username 0 60 7
zhiliao
STORED
```
