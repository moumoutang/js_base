### Function

- Function的length属性，在不能指定默认值的时候，表示的就是定义函数时候的参数个数
- 如果指定了默认参数，那么这个参数将不被算在length里面
- length也不计算rest参数


### 扩展运算符

各种神技

```javascript

[..."hell"]     ["h", "e", "l", "l"]

const [first ,...rest] = [1,2,3,4,5]
first  1
rest   [2, 3, 4, 5]

var arr = [1,2,3]
var  arr1 = [4,5,6]
arr.push(...arr1)

arr  [1, 2, 3, 4, 5, 6]

```
任何类数组对象都可以通过扩展运算符转为真正的对象  

### name属性
name大家都很熟悉了，ES6中的变化就是

```javascript

var test = function(){}
test.name   "test"

```
神奇吧

### 箭头函数
- 注意的一点：函数体内的this就是定义时的对象，而不是使用时的对象
- 特别注意在回调函数里，this的指向
- 其根本原因就是箭头函数内的this根本就没有指向，只能去调用外层的this
- arguments super new.target在箭头函数里不存在，引用arguments的话引用的外层的arguements
- 既然没有自己的this，就不能用call，bind什么的去改变this指向
- 不可以被用作构造函数，否则new会报错

```javascript

function foo(){
  setTimeout(()=> {
    console.log("id",this.id);
    },100);
}

foo.call({ id:33})

id 33  //result

```
### 函数绑定
神奇的 :: 符号    
可以链式写法    
```javascript
  foo :: bar
  bar.bind(foo)
```

### 函数尾调用和尾递归性能优化
### 函数参数尾逗号
