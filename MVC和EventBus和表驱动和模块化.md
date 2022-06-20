# MVC && EventBus && 表驱动 && 模块化



## MVC 三个对象分别对应：

​	model ：数据

​	view : 视图

​	controller ：控制器

它是一个设计模式，万金油，90% 的码多能往里装

```javascript
// view
let html = `<div id='app'>{{n}}</div>`

<script>
	// model
    let n = 1
	// controller
	let docHtml = document.createElement('div')
    docHtml.innerHTML=html.replace('{{n}}',n)
	document.body.appendChild(docHtml)
</script>
```



## EventBus 

三个API ：

on 监听 xxx

off 关闭 xxx

emit 触发 xxx

```javascript
function EventBus(){
    this.eName = []
}
EventBus.prototype.on=function(option){
    
    this.eName.push(option)
    
}
EventBus.prototype.off=function(eName){
    this.eName.forEach((value)=>{
        if(value.eName === eName){
            this.eName.pop(value)
        }

    })
}
EventBus.prototype.emit=function(eName){
    this.eName.forEach((value)=>{
        if(value.eName === eName){
            value.eFn()
        }
    })
}

let test = new EventBus()
test.on({eName:'xxx',eFn:function(){
    console.log('xxx')
}})
console.log('on xxx')
test.emit('xxx')

console.log('off xxx')
test.off('xxx')
test.emit('xxx')

// on xxx
// xxx
// off xxx
```

## 表驱动编程

代码大全》对表驱动编程的描述：

> 表驱动方法是一种使你可以在表中查找信息，而不必用逻辑语句（if 或 case）来把他们找出来的方法。事实上，任何信息都可以通过表来挑选。在简单的情况下，逻辑语句往往更简单而且更直接。但随着逻辑链的复杂，表就变得越来越富于吸引力了。



```javascript
// 使用表驱动
let weeks = {1:"星期一",2:"星期二",3:"星期三"}

let week = 2
console.log(weeks[2])

// if else
if(week === 1){
    console.log("星期一")
}else if(week=== 2){
    console.log("星期二")
}...

// switch case
switch(week){
    case 1:
    console.log("星期一")
    break;
    case 2:
    console.log("星期二")
    break
    default:
    break
}

```



# 我是如何理解模块化的

就是抽离，事不过三

同样的代码写三遍，就抽成一个函数

同样的属性写三遍，就做成共用属性（原型或类）

同样的原型写三遍，就用继承