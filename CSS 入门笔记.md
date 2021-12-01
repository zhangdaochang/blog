# CSS 入门笔记

制定者W3C

lee爵士的挪威同事赖先生

css spec 最权威

css2.1 使用最广泛的

css3 现代版本，分模块



**不要用 width 100%，content-box**

**`outline:1px solid black  | border:1px solid black` border调试**



## 语法

```css
/* 语法一 */
选择器{
    属性名:属性值;
    /* 注释*/
}

/* 语法二：at语法 */
@charset "UTF-8"; /*必须第一行，意思是指定  字符集  但是UTF-8是字符编码 历史遗留问题*/
@import url(2.css); /*从其他地方引入css*/
@media (min-width:100px) and (max-width:200px){ /*媒体查询*/
    /* xxx */
}
```

 **注意事项**

* 所有符号都是英文，写错了，**浏览器会警告（开发者工具会提示）| webStorm 牛x**
* 区分大小写，a 和 A 是不一样的东西
* 没有 // 的注释
* 注意加 **;** 号
* 单位 属性值 不要写错

## border 调试法

* 觉得那个元素有问题，就给这个元素加border
* border 没出现，就是选择器错了或者语法错了
* border出现了，仔细看看样式

## 在哪儿查资料

* 关键词加 MDN
* CSS tricks （英文文档） 关键词加 CSS tricks
* 张鑫旭的博客

## 练习素材

### PSD

* 国外的Freepik 搜索 PSD web
* 365 PSD 的 UI 套件 

### 效果图

* dribbble 很漂亮的   顶级

### 666

* 直接模仿各大网站

**不要沉迷模仿，再多没有增益了就 。当你看一眼就知道大概怎么做就好了**

## 文档流（flow)

* Normal Flow，应该翻译成常规流或者普通流

* inline 从左到右，内容不够就自动截断换行显示

* block  独占一行，从上到下，宽度再窄也不会影响
* inline-block 也是从左到右，地方不够不会截断换行。

## inline元素

* 不接受宽度
* 宽度是由内容决定 的
* 不接受高度，但是可以用padding撑高
* 高度是由line-height间接决定的

## block 元素

* 默认宽度有多宽就多宽 不是100%，是auto
* 可以指定宽度
* 高度是由里面文档流元素决定的，也可以设置高度
* position : absolute |fixed; float 脱离文档流后，会影响高度计算

## inline-block元素

* 可以设置宽度
* 高度是由里面文档流元素决定的，也可以设置高度
* 尽量压窄自己

## overflow 溢出

* 当宽高不够内容会溢出

* 可以加css overflow 属性来设置

* auto是灵活设置，当宽度高度能包裹住，就不会显示滚动条

* scroll 不管宽高能否包裹住，都会显示滚动条

* hidden 超出的部分直接隐藏掉

* visible 是默认的，溢出的内容不管

* overflow-x
* overflow-y

## 盒模型

盒模型里包括 padding + border  + margin + content(自己设置的width)

### content-box

* 宽，高度：`padding*2 + border*2 +content`

### border-box

* 宽，高度：`(content - padding*2 - border*2 ) + padding*2 + border*2`

## margin合并

* 父子margin会合并
* 兄弟margin会合并
* 都是上下合并边距
* 合并时取边距最大的合并

## 阻止margin合并

父子阻止合并 padding | border | overflow : hidden | display : flex挡住 

兄弟合并是符合预期的，但也可用inline-block消除

## 基本单位

### 长度单位

* px 像素单位
* em 自身的font-size 的倍数
* % 百分数
* rem 还不知道
* vh 还不知道
* vw 还不知道

### 颜色单位

* 十六进制     #FF6600 | #F60 必须两个数字一样  12 红  34 绿 56 蓝
* RGBA         rgba(255,127,66,0)   alpha 透明度   | rgb((255,127,66)
* HSL            hsl(150,50%,50%)  色相，饱和度，亮度
* 推荐直接取色

## 布局

布局就是把页面分为一块一块的，从左到右，上到下

### 布局分类

* 固定宽度布局 一般宽度 **960 | 1000 | 1024 px**
* 不固定宽度布局 主要靠文档流的原理来布局 文档流本来就是自适应的，不要加额外的样式
* 响应式布局  意思是PC上固定宽度，手机不固定宽度，混合布局

## float布局 （IE<=9)

### 步骤

* 子元素加 `float : left |right`
* 父元素加 .clearfix `.clearfix:after{content:'';display:block;clear:both}`

### 老手的经验

* 有经验者会留一些空间或者最后一个不设width
* 不需要做响应式,因为手机上没有IE
* IE6/7 会双倍 margin 解决 `_margin-left:5px | display:inline-block`
* padding 上下是高度 一般用px 左右是em 一般0.5 | 0.3
* `vertical-align:middle;`图片底部有多余的用这个去
* 块级元素而且是固定宽度的居中 `margin-left : auto; margin-right : auto; | margin : 0 auto`
* 负margin **平均布局**
* 设置float后margin不会合并

## flex布局（新老浏览器都支持）

CSS Tricks 

### container容器

声明 `display:flex;  display:inline-flex`

```css
.container{
    display:flex; 
 /* or display:inline-flex */
}
```



### flex-direction(主轴方向)

```css
.container{
    		/*    左到右|      右到左  | 上到下  | 下到上 */
    flex-direction:row | row-reverse | column | column-reverse;
}
```

### flex-wrap（折行）

~~~css
.container{
          /*    不折行 | 上到下折行 | 下到上的折行 */
   flex-wrap : nowrap |    wrap   | wrap-reverse;
}
~~~

### flex-flow(简写)

```css
.container {
  flex-flow: column wrap;
}
```



### justify-content(主轴对齐方式)

```css
justify-content : flex-start | flex-end | center | space-between | space -around | space -evenly
```

### align-items(交叉轴对齐方式)

```CSS
.container {
  align-items: stretch | flex-start | flex-end | center;
}
```

[这个更详细点 - Flexbox - CSS-Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

### 老手的经验

* 不要把**宽高**写死，除非有特殊说明。特点不用px或者min max前缀就是不写死
* 必须先给设计稿，没有图不准写代码，没设计稿做个屁。pc和手机端必须的两套
* 没时间只给一套，写错了 不好看 别怪我 和设计师说好
* 公司没设计师，就自己画。让老板看，行了再写。

### 草图工具推荐

* Balsamiq 
* Figma(在线版)
* 墨刀

## Grid布局（支持最新浏览器有可能不兼容其他的旧的浏览器）

* **grid-column-start**  设置列线的开始位置 可以设置负值

* **grid-column-end** 设置列线的结束位置  可以设置负值
* grid-column 缩写形式 `grid-column : 2 / 4`  2是开始位置 4 是结束位置 也可设置一个值 `grid-column :2 ` 这样写就是线的开始位置
* **grid-row-start** 设置行线的开始位置 可以设置负值
* **grid-row-end** 设置行线的结束位置 可以设置负值
* grid-row   缩写形式 `grid-row : 2 / 4`  2是开始位置 4 是结束位置 也可以设置一个值 `grid-row : 2` 这样写就是线的结束位置
* grid-area 行和线的缩写形式 ,`grid-area:1/2/4/6`  row start | column start | row end | column end;
* 如果有很多网格项目,可以覆盖他们;
* **order** 指定一个网格的位置

![image-20211201184823575](https://raw.githubusercontent.com/zhangdaochang/imagesBed/master/images/202112011848314.png)

* grid-template-columns 设置列的宽度 `**grid-template-columns: 20% 20% 20% 20% 20%;**`
* repeat 简写 

![image-20211201185432511](https://raw.githubusercontent.com/zhangdaochang/imagesBed/master/images/202112011854364.png)

* grid-template 缩写形式 

## css position定位

* static 默认值
* relative 相对自己定位
* absolute 一层一层往上找relative  找到了就相对找到的定位
* fixed 固定定位，基准viewport（有诈）
* sticky 粘滞定位 适合做导航条类似的

如果写了absolute ，一般得补一个relative

如果写了absolute  或者 fixed 一定要有top 和left

* 层叠上下文 忘了就搜 mdn

## css动画

动画就是连续播放多张照片 视觉残留

### 渲染步骤包括样式、布局、绘制，合成

[CSS Triggers 渲染触发流程](https://csstriggers.com/)

![image-20211201224457906](https://raw.githubusercontent.com/zhangdaochang/imagesBed/master/images/202112012245818.png)

### 渲染优化

* 使用 transform 和 opacity 属性更改来实现动画-只需要合成更改
* 使用requestAnimationFrame  代替 settimeout 或 setInterval

### transform (变形)

[transform - CSS（层叠样式表 mdn 属性)](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform)

* translateX 左右移动
* translateY 上下移动 
* translateZ 需要设置视点 perspective
* translate 简写
* scale 缩放
* rotate 旋转
* skew  倾斜

### transition (过渡 浏览器补帧)

作用补充中间帧

* transition 属性值 时长  过渡方式[transition-timing-function - CSS（层叠样式表） | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transition-timing-function)  延迟多久开始  

不是所有属性都能补充帧

* display

过渡必须要有开始

```css
.aixin1{
     transition: all 0.5s;
}
.aixin1:hover{
     transform: scale(1.5);
}
```



### animation（动画 自己做帧)

```css
animation: identifier 12s;
@keyframes identifier {
  0% { top: 0; left: 0; }
  30% { top: 50px; }
  68%, 72% { left: 50px; }
  100% { top: 100px; left: 100%; }
}
```

缩写语法

`animation : 时长 | 过渡方式 | 延迟 | 次数 |方向 | 填充模式 | 是否暂停 | 动画名`

* 时长：1s 或者 1000ms
* 过渡方式 : 和 transition 一样 如 linear
* 次数：3 或者 2.4 或者 infinite 重复
* 方向：reverse | alternate | alternate-reverse
* 填充模式： none | forwards | backwards | both
* 是否暂停：paused | running
* 上面所有属性都有对应的单独属性 [animation - CSS（层叠样式表） | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation)

## 感言

根本记不住，现学现用吧！！！！！
