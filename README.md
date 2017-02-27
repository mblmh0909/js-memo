[javascript参考手册](http://www.w3school.com.cn/jsref/index.asp)

目录
*	[基本类型](#一基本类型)
	*	[常用方法](#一常用方法)
	*	[属性选择](#二属性选择)
	*	[子选择器和相邻选择器](#三子选择器和相邻选择器)
	*	[伪类](#四伪类)
*	[显示](#二显示)
	*	[布局](#一布局)
	*	[盒模型](#二盒模型)
	*	[定位](#三定位)
	
### 一、基本类型
#### （一）常用方法
##### Global
	1.编码解码
		encodeURI,decodeURI,encodeURIComponent,decodeURIComponent,escape,unescape
		escape只支持ASCII，弃用。Component多解析/,#,:等符号更彻底
	2.数字
		isFinite比isNaN判断的多。Number比parseInt、parseFloat好用。
	3.代码
		eval字符串代码化，如a["b"]可写为eval("a.b")
##### String
	1.match 参数：字符串或正则表达式；返回：数组
	2.slice,subString,subStr;
		只有subStr第二个参数为长度，不支持副长度
		subString不支持负值自动转0，subStr长度当然不可能是负的也会自转0。
	3.字符串截取后返回新字符串，原字符串不变。
##### Array
	1.转字符串 join(链接符号)。
	2.尾部增取用 push、pop。
	3.头部增取用 unshift、shift。
	4.reverse和sort排序。sort接函数参，函数参返回bool。
	5.splice删除，插入 （index,howmany,insertItem1,2,3(多个)）
	6.与字符串不同。数组变更后原数组改变。
##### Number
	1.toString(进制)
	2.toLocaleString()作用是加,如99,999,999.9999
	3.toFixed(保留小数四舍五入)
	4.isFinite判断NaN和Infinite
