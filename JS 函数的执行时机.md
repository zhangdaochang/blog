# JS 函数的执行时机
```javascript
let a = 1
{
    let a = 2
    console.log(a) //2
}
console.log(a) //1
// 调用时机不同，结果也不一样
```
1. JS 引擎进入一个函数之前，需要把当时的环境保存进调用栈
2.  JS 引擎退出一个函数之前，需要把环境从调用栈里弹出，然后回到这个弹出的环境
3.  调用栈的长度是有限的

```javascript
let i = 0
for(i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}

/*
	1.声明一个作用与当前块（当前js文件）的变量 i 值为 0
	2.for 循环 i=0 开始
	3.判断i<6 true
	4.把setTimeout 和 i 压入栈中 忙完for循环在执行
	5.i++ 此时 i = 1
	6.判断i<6 true
	7.把setTimeout 和 i 压入栈中 忙完for循环在执行
	8.i++ 此时 i = 2
	... 把setTimeout 和 i 压入栈中 忙完for循环在执行
	9.假设此时 i = 5  i<6 true
	10.把setTimeout 和 i 压入栈中 忙完for循环在执行
	11.i++ 此时 i = 6
	12. i<6 false for循环结束
	13. 此时 执行完for 调用栈里的环境 i 已经是 6 了 , 所以执行console.log(i) 会打出 6 执行 6次 6个6
*/
```

## why？

个人理解 ，i 的 作用域为当前的代码块 (js文件)

 ![image-20211209215604173](https://raw.githubusercontent.com/zhangdaochang/imagesBed/master/images/202112092156601.png)

根据就近原则 每次i++ 的都是外边那个 变量 i 。加入调用栈的 i 也是作用域为当前代码块(当前js文件)，for 执行完 i 也就成 6 了  ，在console.log(i) 也就打出了6个6

------

## let 与 for 的组合

**`let`**允许你声明一个作用域被**限制**在 [`块`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/block)级中的变量、语句或者表达式。

```javascript
for(let i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
1.创建一个作用域为 for 代码块里 的 变量 i
2.和之前步骤一样 ， 就是每次压栈的时候 压得都是作用域为for代码块里的i 的值
3.到时候for执行完了，该 console 了，根据栈里的i 的值 打印 。 就是0，1，2，3，4，5
```





------



## 其他方法可以打印出 0、1、2、3、4、5



```javascript
let i = 0
for(i; i<6; i++){
  let j = i
  setTimeout(() => {
    console.log(j)
  }, 0);
}
```

![image-20211209225417673](https://raw.githubusercontent.com/zhangdaochang/imagesBed/master/images/202112092254732.png)

把 j 压到栈中



### 通过call 方式

```javascript
let i = 0
for(i; i<6; i++){
  setTimeout(function(){
    console.log(i)
  }.call(undefined,i), 0);
}

// 两个都行

let i = 0
for(i; i<6; i++){
  setTimeout(function(){
    'use strict'
    console.log(this)
  }.call(i), 0);
}
```

![image-20211209231131342](https://raw.githubusercontent.com/zhangdaochang/imagesBed/master/images/202112092311273.png)

![image-20211209231105003](https://raw.githubusercontent.com/zhangdaochang/imagesBed/master/images/202112092311026.png)



通过指定this 来打印





## 最后有什么理解不到位的，请无情指出。 趁现在思想好改。















