[javascript�ο��ֲ�](http://www.w3school.com.cn/jsref/index.asp)
***
	tips:
	String��function ԭ������ָ����ˡ�����ԭString��function�ǲ���ġ���
	```javascript
	var str = "123"; function func(){};
	str1=str; func1=func;
	str=func;
	func=str1;
	//str1��func1����ԭ�����ַ�������
	```
	��ͬ���ǡ�string�κβ���������ԭ�ַ������У�ԭ�ַ������ò���ı䡣
	function �������Ա��ˣ���prototype��������ԡ���������Ҳ���ˡ�
***
Ŀ¼
*	[��������](#һ��������)
*	[����](#������)
	*	[����](#һ����)
	*	[����](#������)
*	[function](#��function)
	
### һ����������
#### ��һ��Global*
	1.�������
		encodeURI,decodeURI,encodeURIComponent,decodeURIComponent,escape,unescape
		escapeֻ֧��ASCII�����á�Component�����/,#,:�ȷ��Ÿ�����
	2.����
		isFinite��isNaN�жϵĶࡣNumber��parseInt��parseFloat���á�
	3.����
		eval�ַ������뻯����a["b"]��дΪeval("a.b")
#### ������String
	1.match �������ַ�����������ʽ�����أ�����
	2.slice,subString,subStr;
		ֻ��subStr�ڶ�������Ϊ���ȣ���֧�ָ�����
		subString��֧�ָ�ֵ�Զ�ת0��subStr���ȵ�Ȼ�������Ǹ���Ҳ����ת0��
	3.�ַ�����ȡ�󷵻����ַ�����ԭ�ַ������䡣
#### ������Array
	1.ת�ַ��� join(���ӷ���)��
	2.β����ȡ�� push��pop��
	3.ͷ����ȡ�� unshift��shift��
	4.reverse��sort����sort�Ӻ����Σ������η���bool��
	5.spliceɾ�������� ��index,howmany,insertItem1,2,3(���)��
	6.���ַ�����ͬ����������ԭ����ı䡣
#### ���ģ�Number
	1.toString(����)
	2.toLocaleString()�����Ǽ�,��99,999,999.9999
	3.toFixed(����С����������)
	4.isFinite�ж�NaN��Infinite
### ��������
#### ��һ������
	1.constructor
		ָ��ö���Ĺ��캯����ָ���乹�캯����
		���ж���Ĺ��캯�����ǣ�function�Ĺ��캯����function��
#### ����������
	1.hasOwnProperty(property)
		�ж��Ƿ�ӵ�����ԡ����ų�ԭ������
	2.isPrototypeOf(object)
		object��ԭ�������Ƿ��и�ԭ�Ρ�
		�������ж��ǲ���ĳ���Զ�������ʵ��
		```javascript
		function Rectangle() {}
		var rec = new Rectangle();
		Rectangle.prototype.isPrototypeOf(rec); Rectangle��ԭ���Ƿ���rec��ԭ������
		```
	3.propertyIsEnumerable
		��������Ƿ��ܱ�ö�ٳ���
### ����function
#### ��һ������
	1.prototype
		Ĭ������constructorָ��������
	2.argument
		���յ��Ĳ�����argument.callee���ر�����2
	3.this
		˭���õ�һ��һ�������ң��ҵ�Ϊֹ��
#### ����������
	1.call��apply��bind
		Ŀ����Ϊ�˱���˭�����ˡ���չthis��
		bind������ִ�С�apply��argument���顣