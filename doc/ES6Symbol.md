### Symbol
传说中js的第七种数据类型，指的就是独一无二的值；     
-  不能用new   var sy = Symbol()
- 在object定义时要使用[]

```
let s = Symbol("foo");
let t = Symbol("foo");//它们两并不相等
let obj = {
  [s] : function(arg){ ... }
}

obj.s //这种方法也不可以  必须obj[s]

```
- Symbol当属性时不是私有属性，而是公有的，但是不能被一般的属性循环循环出来，必须用getOwnPropertySymbols方法来循环出Symbol类型属性
-  Symbol.for 用于一种场景，当想用同一个Symbol的时候，使用Symbol.for(value)来声明的时候,会先查找是否已经有用value值来做为标记的Symbol了，如果已经有则返回同一个，没有则新建一个

```
var s = Symbol.for({1:1})
var  t = Symbol.for({1:1})

t === s //true
```
- Symbol.keyFor返回该Symbol对应的value值

- 内置的 Symbol值
      - Symbol.iterator 指向其默认的迭代器，在 for of中会被用到，可以对一个对象定义自己的Symbol.iterator函数，那么就可以使用for of进行循环
