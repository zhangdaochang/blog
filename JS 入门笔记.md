# JS 入门笔记

## 软要求

1. 逻辑能力

2. 质疑自己

3. 抽象能力

## 硬要求

### 足够的代码量

达到 1000 行 -新手

达到 10000 行 -熟手

达到 50000 行 -专业选手

**安装 cloc 工具可以用来统计一个仓库里的有效代码**

附一：只能时间积累

附二：把仓库里不相关的写进 .gitignore 文件

### 了解足够的概念（会用会说）

1. 闭包，原型

2. 类，继承

3. MVC，Flux

4. 高阶函数

5. 前端工程化

附一：在课程中提炼

附二：大脑中思考

附三：在博客上总结

附四：在代码中实践

## 踩坑经验

专家就是把该领域所有的错误都犯完的人。

**如何踩坑？**

做项目，而且是个人项目。这样才能全方位踩坑

## JS与ECMAScript 的关系

ECMAScript 是 纸上的标准 ，JS  是浏览器的实现

纸上标准往往落后于浏览器，先实现，再写进标准



## JS 的兴起

1. Gmail 发布后开始的
2. 国内2010年左右兴起的

## JavaScript 的爆发

* Chrome JS 引擎 V8
* 2009 年，Ryan 基于V8创建的 Node.js
* 2010 年，Isaac 基于 Node.js 写出了npm
* 同年 TJ 受 Sinatra 启发，发布了Express.js
* 从此前端可以愉快的写后端应用了

[JavaScript 的10个设计缺陷](http://www.ruanyifeng.com/blog/2011/06/10_design_defects_in_javascript.html)

## JS 引擎

编译

优化

执行

垃圾回收



## Stack 和 Heap 区别

Stack 是顺序存放的

Heap 是随机存放的

数据分为两种：非对象和对象

非对象都存在 Stack 区

对象都存在 Heap 区

= 号总是会把右边的内容复制到左边



## JS的三座大山

1. this
2. 原型（ prototype）
3. AJAX

## 每个对象都有隐藏属性

![3f467d0068847764b2cfc3d4ae8d2da](https://raw.githubusercontent.com/zhangdaochang/imagesBed/master/images/202112050001787.jpg)

