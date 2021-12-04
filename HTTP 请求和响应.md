# HTTP 请求和响应

HTTP 标准是 RFC2612

服务器就是一个没有屏幕的电脑，可以用 ip 访问他

帮你发请求的工具叫做用户代理 （ User-Agent)



## 请求

动词 + 路径加查询参数 + 协议名/版本

HOST : 域名或者 IP

Accept : text/html

Content-Type : 请求体的格式

回车

请求体



附一 ：动词包括 `GET | POST | PUT | PATCH | DELETE`

附二 ：GET 请求是一般是没有请求体的

附三 ：GET 请求 POST 上传

## 响应

协议名/版本 状态码 状态字符串

Content-Type ：响应体格式

回车

响应体



附一 ：常见的状态码 

- 100~199 **消息**  服务器已经收到请求头，请求者应当继续提出请求。服务器返回此代码表示已收到请求的第一部分，正在等待其余部分
- 200-299 **成功**  
- 300 -399 **重定向**
- 400-499 **客户端出错**
- 500-599 **服务器出错**

## curl 构造请求

### 设置请求动词

-X POST

注意大小写

### 设置路径和查询参数

直接在 URL 后面加

### 设置请求头

-H 'Name : Value' 或者--header  'Name : Value' 

### 设置请求体

-d '内容' 或者 --data '内容'

## Node.js 读请求

### 读取请求动词

request.method

### 读取路径

request.url 路径+查询参数

path 纯路径，不带查询参数

query 只有查询参数

### 读取请求头

request.headers['Accept']

### 读取请求体

还没

## Node.js 设置响应

### 设置响应状态码

response.statusCode = 200

### 设置响应头

response.setHeader('Content-Type','text/html');

### 设置响应体

response.write('内容')

可以追加内容



附一：出错了就 console.log()