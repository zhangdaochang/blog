# 浅析 URL

超文本传输协议（Hyper Text Transfer Protocol，*HTTP*）

internet protocol 是 IP

## IP 分为外网和内网

从电信租用宽带。

从 ip138.com 获取自己分配到的外网 ip

如果重启路由器可能会重新分配一个外网ip



内网路由器会在家里创建一个内网，内网中的设备使用的是内网 ip ，cmd > ipconfig , 

内网格式 192.168.x.x , 路由器有两个 ip 一个内网 ip 一个外网 ip

路由器像一个转发器，有时候路由器也被叫做网关

最大255.255.255.255



可以用 ping 命令 看百度的ip

```bash
ping www.baidu.com
```



### 几个特殊的 IP

127.0.0.1 自己

localhost 通过 hosts文件指向自己 `C:\Windows\System32\drivers\etc\hosts`文件

0.0.0.0 不表示任何设备



## 端口 port

一个服务一个端口，[TCP/UDP端口列表 - 维基百科，自由的百科全书 (wikipedia.org)](https://zh.wikipedia.org/wiki/TCP/UDP端口列表#0.E5.88.B01023.E5.8F.B7.E7.AB.AF.E5.8F.A3)

可以提供65535 个端口，0 ~ 1023 是系统保留的要想用就用管理员权限，ip 和 端口缺一不可

HTTP 80 端口

HTTPS 443 端口

FTP 21 端口



## 域名

域名就是对ip 的别称，可以 ping baidu.com ,获取对应的 ip 地址

一个域名可以对应不同ip，这个叫做负载均衡

一个 ip 可以对应不同域名， 这个叫共享主机

1. com是顶级域名
2. baidu.com 是二级域名（俗称一级域名）
3. www.baidu.com 是三级域名 （俗称耳二级域名）
4. 一级和二级域名 是父子关系



## DNS（Domain Name System）

DNS 就是 把域名和 ip 对应起来



请求一个域名会先从 dns 获取到域名对应的 ip 然后再通过 ip 请求

```bash
λ nslookup baidu.com
服务器:  UnKnown
Address:  2400:3200::1

非权威应答:
名称:    baidu.com
Addresses:  220.181.38.251
          220.181.38.148
```



## 路径

查看不同的页面 就是通过路径做到的



## 参数

同一个页面同一个路径，不同的内容 ，参数做得到



## 锚点

 同一个页面同一个路径同一个内容，不同的位置 锚点可以做到

 锚点是不会传给服务器的。



## URL（统一资源定位符）

协议 + 域名或 ip + 路径 + 参数 + 锚点 = URL

![image-20211203142829022](https://cdn.jsdelivr.net/gh/zhangdaochang/imagesBed@master/images/202112031428061.png)

​																																                                  **图片来自饥人谷**

## HTTP协议

HTTP协议是基于 TCP / IP 两个协议



## CURL 命令

`curl -v http://baidu.com`

`curl -s -v  -- https://www.baidu.com`

### curl 请求过程

1. 如果url后面没有 ‘/’ 会加上
2. 请求 DNS 获取域名对应的 IP
3. 进行TCP 连接，成功后发送HTTP 请求
4. 获取响应
5. 关闭TCP连接
6. 真正关闭
