Who is listening on a given TCP port on Mac OS X?
```
lsof -n -i4TCP:5000
lsof -i -n -P | grep 5000
```
```
$ lsof -n -i4TCP:5000 | grep LISTEN
COMMAND  PID USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
python  8845   yq    3u  IPv4 0xb4638e65ab785dd9      0t0  TCP *:commplex-main (LISTEN)
```

加sudo能看到root 用户的
```
sudo lsof -i -n -P | grep TCP
```
不加sudo只能看到当前用户的, 
# -i select IPv[46] files 
# -n no host names
# -P no port names
查看本机IP相关的链接，不反解主机名（IP以数字格式显示），不反解端口名（端口以数字格式显示）
```
lsof -i -n -P
```
查看5000端口的连接
```
lsof -i -n -P| grep 5000
lsof -i:5000
```

