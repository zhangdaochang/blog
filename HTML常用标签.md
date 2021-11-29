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

```html
<a id="xxx" href="https://www.qq.com">打开QQ</a>
<a href="http:////baidu.com">打开baidu http协议</a>
<a href="./c.html">自己的路径</a>
<a href="//baidu.com">继承关系打开百度</a>
<a href=" javascript:alert('1');">js alert</a>
<a href=" javascript:;">不做操作</a>
<a href="mailto:xxx@qq.com">邮箱</a>
<a href="#">顶部</a>
<a href="#xxx">调转到指定的 id 标签</a>
<a href="tel:10086">打电话</a>
<a href="//www.baidu.com" target="_blank">新标签页面打开</a>
<a href="//www.baidu.com" target="_self">当前页面打开</a>
<a href="//www.baidu.com" target="xxx">在名为xxx的标签页面打开</a>
```



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

```html
 <table style="table-layout: fixed">
        <tfoot>
            <tr>
                <th>每周更新</th>
            </tr>
        </tfoot>
        <tbody>
            <tr>
                <th>早上</th>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
            </tr>
            <tr>
                <th>中午</th>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
            </tr>
            <tr>
                <th>晚上</th>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
                <td>茄子肉末</td>
            </tr>
        </tbody>
        <thead>
            <tr>
                <th>时间</th>
                <th>周一</th>
                <th>周二</th>
                <th>周三</th>
                <th>周四</th>
                <th>周五</th>
                <th>周六</th>
                <th>周日</th>
            </tr>
        </thead>
    </table>
```



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

```html
<img src="https://thirdwx.qlogo.cn/mmopen/vi_32/JESzicQgN4smSYeCHeAw06QSa0uAVOsC6bLrO8H9hR34bRrXGTFcbou4CkicSPZkIUjd3ic75bEZB0kS88vePEL1g/132" alt="企鹅" width="20%">
```



## form 标签

### 属性

action 请求路径

method 请求方式 默认GET 还有POST

autocomplete 配合input的name属性 会自动推荐要写什么 

target 参考 a 的 target

**一个form里的标签里必须要有一个type 等于 submit的属性**

```html
    <form action="yyy" method="POST" autocomplete="on">
        你的邮箱
        <input type="text" name="mail">
        <input name="file" type="file" multiple>
        你最爱的颜色
        <input name="color" type="color">
        你的性别
        <input type="radio" name='sex' value="男">男
        <input type="radio" name='sex' value="女">女
        <input type="password" name='passwd'>
        你的爱好
        <input type="checkbox" name='ruby' value="c">C
        <input type="checkbox" name='ruby' value="t">T
        <input type="checkbox" name='ruby' value="R">R
        <input type="checkbox" name='ruby' value="L">L
        <input type="submit">
    </form>
<!-- name值会传到后端 -->
```



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

```html
<input type="text" name="mail">
<input name="file" type="file" multiple name="userfile">
你喜欢的颜色
<input name="color" type="color" name="rColor">
你的性别
<input type="radio" name='sex' value="男">男
<input type="radio" name='sex' value="女">女
输入密码
<input type="password" name='passwd'>
你的爱好
<input type="checkbox" name='ruby' value="c">C
<input type="checkbox" name='ruby' value="t">T
<input type="checkbox" name='ruby' value="R">R
<input type="checkbox" name='ruby' value="L">L
```



## textarea 多行文本

### css 

resize:none; 大小不可被用户拖动

```html
<textarea name="yJieshao" style="resize:none;height:600px"></textarea>
```



## select +option 下拉列表

option 的value属性是真正的值 标签包裹的是用户看到

option包裹不了input

~~~html
<select id='aaa' name="666">
    <option value="uncity">请选择你的城市</option>
    <option value="beijing">北京</option>
    <option value="hangzhou">杭州</option>
    <option value="test"><input type="text">包裹不了</option>
</select>
~~~



## 学习感想

一定要写出来，才会加深印象。

用id获取

value是给js看的 



form 标签里的子标签只有带name值才会传到后端