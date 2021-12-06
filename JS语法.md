# JS语法

**浮点数运算不准确**

**使用最没有歧义的写法**

**大小写敏感**

**大部分回车和空格没有实际意义。不影响断行就行**
**return 后面不能空格和回车 ，会返回 undefined**
注释 ：**踩坑注释 | 为什么代码这么奇怪，遇到什么bug**

## 标识符

标识符只能包含字母或数字或下划线（“_”）或美元符号（“$”），且不能以数字开头。标识符与字符串不同之处在于字符串是数据，而标识符是代码的一部分。在 JavaScript 中，无法将标识符转换为字符串，但有时可以将字符串解析为标识符。--mdn

![image-20211205214309934](https://raw.githubusercontent.com/zhangdaochang/imagesBed/master/images/202112052143354.png)

图片来自 饥人谷

## 语句 和 表达式

一般情况下，每一行就是一个语句。

```javascript
var a = 1 + 3; //赋值语句
```

为了得到返回值的计算式叫做表达式

`1 + 3` 表达式

![image-20211205211302042](https://raw.githubusercontent.com/zhangdaochang/imagesBed/master/images/202112052113607.png)

图片来自 饥人谷

## 区块 block(把代码包起来)

~~~javascript
{
    let a = 1
    let b =2
}
~~~

## if 语句

if(表达式){语句1} else {语句2}

{可以省略，省略的话 if 只会看第一行语句}

``` javascript
//简写
a=1
if(a=3){
    console.log('a=3')
   	console.log('a=1')
}else if(a===3){
    console.log('a等于三')
}
// 繁写
a=1
if(a=3){
    console.log('a=3')
   	console.log('a=1')
}else{
    if(a===3){
        console.log('a等于三')
    }
}
   
// 变态情况
a=1
if(a=3)
   console.log('a=3')
   console.log('a=1')
```

## switch 语句

```javascript
switch(待匹配){
     case 匹配：
    	break
     case 匹配：
    	break
     default:
        break;
}
```

* 大部分不要省略break
* 不要忘记写default



## 三元表达式

表达式1 ? 表达式2 : 表达式3

`a>b ? true : false`

## && 且

`console && console.log && console.log('hi')` 这句会打出 'hi'

`A && B && C && D` 取第一个假值或 D，并不会取true / false

## || 或

`A && B && C && D`	取第一个真值或 D, 并不会取true / false

`A = A || B` B 就是A 的保底值

## while 循环语句

while(表达式){语句}

判断表达式的真假，真的执行语句 ，假的话执行后面的语句

```javascript
var i = 0
while (i<10){
    console.log(i)
    i = i + 1
}
// 会多打个10
```

## for 循环

```javascript
for（语句1;表达式2;语句3){
	//先语句1
    //表达式2
    //语句3
    //表达式2
    //语句3
}
for (var i=0,i<5;i++){
    console.log(i)
}
```

break 遇到 break 直接结束当前循环

continue 跳出这一次循环

## label 标记

详细教程

[JavaScript 的基本语法 - JavaScript 教程 - 网道 (wangdoc.com)](https://wangdoc.com/javascript/basic/grammar.html#标签label)

[label - JavaScript | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/label)

```javascript
{
    foo:1
}
// 把1 标记成foo
```



## 数字与字符串

数字就是数字 ，字符串就是字符串

数字是用64位浮点数的形式储存的

字符串是用类似 UTF8  形式储存的(UCS-2)

## 数据类型

1. number JS 的 number 全都是以小数（浮点数）的形式存储的，没有单独的整数

2. string

   ``` javascript
   \' 表示 '
   \" 表示 "
   \n 表示 换行
   \r 表示回车
   \t 表示 tab 制表符
   \\ 表示 \
   \uFFFF 表示对应的 Unicode 字符
   \xFF 表示前 256 个 Unicode 字符
   `it 's ok` "it 's ok" 'it "s ok' 特殊组合转义
   ```

   

3. bool falsy 值 ：0 NAN '' undefined null

4. symbol  生成一个全局唯一的值。

5. undefined

6. null

7. object

8. bitint  [MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/BigInt)

## 类型转换

[类型转换 · JavaScript 秘密花园 -)](https://www.javascriptc.com/books/javascript-garden/types/casting.html)



## 变量声明

变量声明的时候同时指定了类型。

`var | let | const`

var : 过时的，不好用的方式

let : 更合理的方式

```javascript
// 只作用于块内
{
    let b =1
    console.log(b) //1
}
console.log(b)//  b is not defined
// 不能重复声明
{
    let a = 2
    let a = 1
}
//VM581:3 Uncaught SyntaxError: Identifier 'a' has already been declared
// 声明赋值不赋值都行
{
    let a
}
// 不能在为声明之前使用
{
    console.log(b)
    let b = 1
}
// Cannot access 'b' before initialization

// 全局声明let 不会变成 window 属性
let bbb = 3

window.bbb
undefine
```



const : 声明时必须赋值，不能再改。和常量的意思一样



**写代码推荐使用 let 和 const  不许用 var**

