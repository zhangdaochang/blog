# CSS 入门笔记

制定者W3C

lee爵士的挪威同事赖先生

css spec 最权威

css2.1 使用最广泛的

css3 现代版本，分模块



**不要用 width 100%，content-box**



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