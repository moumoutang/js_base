## 第三篇  字符串扩展
#### unicode表示
- js之前只支持\u0000 - \uFFFF之间的unicode字符
- 如果超出这个范围就只能用双字节表示
- 6版本对此进行了改进 可以使用 \u{20BB7}来表示四字节的字符

#### codePointAt
- js之前的charCodeAt 不能完整识别4字节的字符串
- 可以用此方法来判断是不是四个字节的字符，取值与0xFFFF进行比较就可以得出

``` javascript
var a = "🐔"//这是一个四个字节的字符
a.length
2
a.charAt(0)
"�"
a.charAt(1)
"�"
a.charCodeAt(0)
55357
a.charCodeAt(1)
56340
a.codePointAt(0)//此方法能准确识别第一个
128020
a.codePointAt(1)//但是后面一位还是认的第一个字符的后两个字节
56340

//用for of 可以准确循环出
for(let ch of a){console.log(ch.codePointAt(0))}
VM611:1 128020

```
#### fromCode

旧版本也有，感觉很少用，就是从unicode的反转，但是之前也是同样的不支持四字节字符，新版本支持

``` javascript
String.fromCodePoint(0x20bb7)
"𠮷"
```

#### 字符串遍历
```
for of //比传统的有点是可以识别大于FFFF的字符，如上所述

```

#### At
 功能同charAt相同，同样扩展了识别范围

#### 各种新方法
```
//以下方法都支持第二个参数，表示搜素的起始位置
includes 顾名思义了，返回boolean
startsWith
endWith

// 将一个字符串重复N次
// 参数为数字，不是会先转为数字，小数会被取整，小于1则为0结果为空字符串
repeat

padStart  padEnd  //根据设定的字符串长度和字符来补全字符串，貌似现在支持的不是很好


```

#### 模板
神奇的反引号`  mac 键盘偏左上方的那个键~~~~
- 普通的字符串也可以用，换行字符串也可以用
- 如果使用模板，反引号内的换行和空格都会被保留下来
- {}内可以放变量，也可以放表达式

  
```
var name = "Bob",time = "today";
`Hello ${name}`
"Hello Bob"
```
