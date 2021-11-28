# HTML入门笔记1

## html 认识

html 是 lee 爵士发明的 超文本标记语言

html 应该首先该写什么

```html
<!DOCTYPE html> <!--告诉浏览器我是html，请用html来解析我-->

<html lang="zh-CN"> <!-- 设置语言为 中文简体 -->
<head>
    <meta charset="UTF-8"> <!-- 设置编码 utf-8 -->
    <meta http-equiv="X-UA-Compatible" content="IE=edge"> <!-- 告诉浏览器用最新内核-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- 在手机上禁用缩放 -->
    <title>Document</title> <!-- 标题 -->
</head>

<body>

</body>

</html>
```



## 标签的几种形式

**<!DOCTYPE html>** 告诉浏览器我是html，请用html来解析我

**<tag attr=value>内容</tag>** 常规标签

**<tag  attr>内容</tag>**  input 标签的 checked 属性就是这样

**<tar attr=value>**   新版闭合应该这样写

## 细节

大小写没区别

双引号只有特殊符号在加 比如空格

注释的写法：<!--我是注释-->

## 体系化学习

学会语法  比如 学会标签的几种形式

如何调试  比如 用 idea 工具

在哪儿查资料   比如 从 mdn

标准制定者是谁 比如 W3C lee 爵士

&copy;  `&copy;  `

## 标签全局属性
```bash
class # .xxx
id   # 确保真的唯一再用   xxx.style   如果像top，self之类的 需要document.getElementById('xxx')
style # 优先级比css高  js>style>css
contenteditable # 可被编辑
hidden # 消失
tabindex # 我鼠标坏了？ tab ↓ shift+tab ↑   -1 tab 键切不到
title # 鼠标悬浮上可查看
```

## css reset

```css
/* 转自 FrankFang | https://gist.github.com/FrankFang/df5e57a0799823ed89a960a642b3a1e2 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
*::before,
*::after {
  box-sizing: border-box;
}
a {
  color: inherit;
  text-decoration: none;
}
input,
button {
  font-family: inherit;
}
ol,
ul {
  list-style: none;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
```

## 章节标签

```bash
h1~h6 # 标题 大小 1>2>3>4>5>6
section # 章节
article # 文章
main # 主要内容
p # 段落
header # 头部
footer # 脚步 底部 一般加版权声明什么的 &copy;
aside # 可以做导航
div # 用来做划分
```



## 内容标签

```bash
ol + li # 有序列表
ul + li # 无需列表
dl + dt + dd # dl dt 被描述 dd 描述内容
pre  # 保留 空格 tab 回车 ...  font:inherit
code # 被 code 包括会成等宽字体
hr # 分割线
br # 换行
a # 链接 加上 target="_blank" 新窗口打开 不加当前页面打开
em # 斜体 ...语气
strong # 加粗 ...本质
qoute # 引用
blockquote # 另起一行的引用
```

