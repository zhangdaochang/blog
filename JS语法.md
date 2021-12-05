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

