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
