# HTML常用标签

## a 标签

### href

* https 协议
* http 协议
* //google.com 继承协议 当前页面是什么协议就会自动使用当前的协议
* /index.html 自己目录的路径
* 伪协议 javascript:alert('1');  |   javascript:; | mailto:xxx@qq.com 邮箱 |  tel:10086 手机号码   |# 会滚到顶部 | #xxx 调转到指定的 id 标签

### target

*  _blank  新窗口打开
* _top 在iframe的最上级打开 一帮配合iframe用
* _parent 在父级窗口打开 一帮配合iframe用
* xxx 如果没有xxx的窗口创建一个名为xxx的窗口，如果有就在xxx的窗口打开 也可以配合iframe用
* .self 在当前窗口打开

### download 一般不用，大部分不支持

### rel= noopener 后面学js会用到



## iframe 标签 现在用的少了

## table标签（如果thead和tbody、tfoot的顺序反了也没事，都会按照thead>tbody>tfoot的顺序排列）

### thead(一般可以没有)

tr 行

th 也是数据，只不过加粗了

### tbody

th 也是数据，只不过加粗了

tr 行

td 数据

### tfoot(一般可以没有)

th 也是数据，只不过加粗了

tr 行

td 数据

### table 的样式

table-layout:auto # 自动计算列的宽度 自适应的

table-layout:fixed #  自动计算列的宽度 等宽的

border-spacing:20px # 单元格之间的间距

border-collapse:collapse # 清除单元格之间的间距

## img 标签

### 属性

src 图片地址 ，作用发出一个get请求，来展示图片

alt 图片显示失败了就显示描述

height 高度 只写高度 宽度会自适应

width 宽度 只写宽度 高度会自适应  **都写了宽高的话图片会变形，前端一定不要让图片变形 **

### js

onload 图片加载成功会怎么做

onerror 图片加载失败会怎么做   xxx.src

### css 响应式

width:max-width:100%

## from 标签

### 属性

action 请求路径

method 请求方式 默认GET 还有POST

autocomplete 配合input的name属性 会自动推荐要写什么 

target 参考 a 的 target

**一个from里的标签里必须要有一个type 等于 submit的属性**

## input标签

required 必需要写的 不能留空

### type属性

text 文字输入框

color 颜色选择框

password 密码属虚诳

radio 单选选择框 需要给个name

checkbox 多选选择框 需要给个name

file 文件选择框 加上multiple 上传多个文件

hidden 给js看的，用户看不见

### 事件

onchange 当输入改变的时候

onfocus  当获得焦点的时候

onblur 当失去焦点的时候

## textarea 多行文本

### css 

resize:none; 大小不可被用户拖动

## select +option 下拉列表

option 的value属性是真正的值 标签包裹的是用户看到

option包裹不了input

## 学习感想

一定要写出来，才会加深印象。