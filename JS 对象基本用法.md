# JS 对象基本用法

* 无序的数据结合
* 键值对的形式

## 写法

```javascript
let obj = {'name' : 'xiaoming','age':18}
let obj = new Object({'name' : 'xiaoming'})
console.log({'name' : 'xiaoming','age':18})

Object.keys(obj) //会打出键名
```

## 细节

* 键名是字符串，不是标识符，可以包含任意字符串

* 引号可以省略，省略后就只能遵守标识符写了，就算引号省略了，他还是字符串
* 用 [a] , 会把a的变量值 做键名

## 隐藏属性

JS 中 每一个对象都有一个隐藏属性

隐藏属性 储存这原型的地址

原型就是一个对象

原型对象里的属性就是共有属性

好处 省

**对象的原型也是的对象**

对象的原型的原型是 null

## 删

``` javascript
let obj = {'name' : 'xiaoming','age':18}
 // 删

obj.name = undefined // 属性还在,值没了变成 undefined
delete obj.name  // 会把属性 和值一起删掉
delete obj['name'] // 会把属性 和值一起删掉

delete obj // 删不了

```

## 查

```javascript
let obj = {'name' : 'xiaoming','age':18}

Object.keys(obj) // 读对象的自身 key
Object.values(obj) // 读对象的自身 value
Object.entries(obj) //读对象的自身 key + value
console.dir(obj) // 读对象的 共有(隐藏)属性 和 自身属性 所有的key + value
obj.__proto__ //读对象的 共有(隐藏)属性

'toString' in obj // 查看对象自身和共有属性是不是有 toString
obj.hasOwnProperty('toString') //判断一个属性是自身里有没有 toString
obj.xxx === undefined // 不能判断xxx是否在对象中

obj['name'] // 读 name 的 值
obj.name 等于 obj['name'] 不是 obj[name]

let name = 'name'
obj[name]等于 obj['name']

```

## 改 增(如果有了就是改，没有就是增)

```javascript
let obj = {'name' : 'xiaoming','age':18}
// 修改 或 增加

//直接赋值
obj.name = 'xiaohong'
obj['name'] = 'xiaohong'
let name = 'name'; obj[name] = 'xiaohong'
obj['na'+'me'] = 'xiaohong'
obj['ppp'] = 'ppp'
//批量赋值
Object.assign(obj,{p1:1,p2:2,p3:4})

obj.toString = 'xxx'  // 不会修改到共有属性，会在自身加个toString 属性
```

**修改隐藏属性 原型**

```javascript
// 不推荐
let obj = {'name' : 'xiaoming','age':18}
let common = {'国籍':'中国'}

obj.__proto__ = common

//推荐

let common = {'国籍':'中国'}
let obj = Object.create(common)
Object.assign(obj,{p1:1,p2:2,p3:4})
```

