# memcached
```
安装
sudo apt install memcached
启动
service memcached start
前台启动
/usr/bin/memcached -u memcache start
-d 表示后台启动
/usr/bin/memcached -u memcache -d start
登陆其它主机的memcached，启动命令
/usr/bin/memcached -l 0.0.0.0 -u memcache -d start
本机登录memcache
telnet 127.0.0.1 11211
  
  
```
