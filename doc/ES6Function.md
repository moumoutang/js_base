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
