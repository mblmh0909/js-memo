[javascript参考手册](http://www.w3school.com.cn/jsref/index.asp)
***
	tips:
	String和function 原变量的指向变了。但是原String和function是不变的。即
	```javascript
	var str = "123"; function func(){};
	str1=str; func1=func;
	str=func;
	func=str1;
	//str1和func1还是原来的字符串或函数
	```
	不同点是。string任何操作都不在原字符串进行，原字符串引用不会改变。
	function 本身属性变了，或prototype添加了属性。其他引用也变了。
***
目录
*	[基本对象](#一基本对象)
*	[对象](#二对象)
	*	[属性](#一属性)
	*	[方法](#二方法)
*	[function](#三function)
	
### 一、基本类型
#### （一）Global*
	1.编码解码
		encodeURI,decodeURI,encodeURIComponent,decodeURIComponent,escape,unescape
		escape只支持ASCII，弃用。Component多解析/,#,:等符号更彻底
	2.数字
		isFinite比isNaN判断的多。Number比parseInt、parseFloat好用。
	3.代码
		eval字符串代码化，如a["b"]可写为eval("a.b")
#### （二）String
	1.match 参数：字符串或正则表达式；返回：数组
	2.slice,subString,subStr;
		只有subStr第二个参数为长度，不支持副长度
		subString不支持负值自动转0，subStr长度当然不可能是负的也会自转0。
	3.字符串截取后返回新字符串，原字符串不变。
#### （三）Array
	1.转字符串 join(链接符号)。
	2.尾部增取用 push、pop。
	3.头部增取用 unshift、shift。
	4.reverse和sort排序。sort接函数参，函数参返回bool。
	5.splice删除，插入 （index,howmany,insertItem1,2,3(多个)）
	6.与字符串不同。数组变更后原数组改变。
#### （四）Number
	1.toString(进制)
	2.toLocaleString()作用是加,如99,999,999.9999
	3.toFixed(保留小数四舍五入)
	4.isFinite判断NaN和Infinite
### 二、对象
#### （一）属性
	1.constructor
		指向该对象的构造函数，指向其构造函数。
		所有对象的构造函数都是，function的构造函数是function。
#### （二）方法
	1.hasOwnProperty(property)
		判断是否拥有属性。即排除原型属性
	2.isPrototypeOf(object)
		object的原形链中是否含有该原形。
		多用于判断是不是某个自定义对象的实例
		```javascript
		function Rectangle() {}
		var rec = new Rectangle();
		Rectangle.prototype.isPrototypeOf(rec); Rectangle的原形是否再rec的原型链中
		```
	3.propertyIsEnumerable
		检测属性是否能被枚举出。
### 三、function
#### （一）属性
	1.prototype
		默认属性constructor指向函数本身。
	2.argument
		接收到的参数。argument.callee返回本函数2
	3.this
		谁调用的一层一层往上找，找到为止。
#### （二）方法
	1.call、apply、bind
		目的是为了便于谁调用了。扩展this。
		bind不立即执行。apply接argument数组。