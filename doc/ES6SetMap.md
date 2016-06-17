## Set
类似于数组   
但是里面的元素都是唯一的没有重复,但插入的值都不会发生类型转换  
set可以接受数组或者类数组参数进行初始化

```
var test = new Set([1,2,2,3,4,5,6])

test
Set {1, 2, 3, 4, 5, 6} //不会添加两个重复的项进去的

var test1 = new Set([{},{}])

test1
// Set {Object {}, Object {}} 但是两个对象不能确定是不等的

test1.delete({})
// false 既然都不相等自然也就删除不掉

test1
Set {Object {}, Object {}}

```
### WeakSet

成员只能是对象，但是其中都是弱引用，其他对象都不能引用该对象，里面的对象随时会被回收，不能被遍历，没有size；    
那有啥用呢？    
可以引用dom，不用担心在dom被删除时内存泄漏

## Map

```
var m = new Map()

m.set({},5)
m.set({},5)

//Map {Object {} => 5, Object {} => 5}  两个对象指向不同的内存地址，所以不被认为是同一个key值，所以size仍为2

m.size
2

var map = new Map([["name","张三"],["title","Author"]]) //也可以这么初始化

Map {"name" => "张三", "title" => "Author"}


```

###  WeakMap
只接受对象作为键名，null除外，同样键名所指向的对象不计入垃圾回收器,随时可能被回收，被回收后WeakMap撤销对应的键值对，可以用于防止内存泄漏；
