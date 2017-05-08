#H5 本地存储
##cookie存储永久数据存在以下几个问题：
  1. 大小：cookie的大小被限制在4kb
  2. 带宽：cookie是随着HTTP事务一起被发送的，因此会浪费一部分发送cookie时使用的带宽
  3. 复杂性：要正确的操控cookie是很困难的
##什么是web Storage功能
   在web上存储数据的功能，这里的存储是针对客户端本地而言，具体分两种：

* sessionStorage（临时保存）
	* 将数据保存在session对象中，所谓session是指在用户在浏览某个网站时，从进入网站到浏览器关闭所经过的这段时间，也就是用户浏览这个网站所花费的时间
	* session对象可以用来保存在这段时间内所要求保存的任何数据。
* localStorage （永久保存）
	* 将数据保存在客户端本地的硬件设备
>###兼容浏览器<br/>
>Firefox3.6以上<br/>
>Chrome6 以上<br/>
>Safari5 以上<br/>
>Opera10.5 以上<br/>
>IE8 以上
##简单例子：
	<!DOCTYPE html>
	<html>
	<head>
		<meta charset="utf-8" />
		<title></title>
	</head>
	<body>
		<p id="msg"></p>
		<input type="text" id="input"/>
		<input type="button" value="保存数据" onclick="saveStorage('input')"/>
		<input type="button" value="读取数据" onclick="loadStorage('msg')"/>
	</body>
	<script src="js/script.js"></script>
	</html>
###sessionStorage模式script.js文件如下：
	//sessionStorage 临时存储
	function saveStorage(id){
		var target =  document.getElementById(id);
		var str = target.value;
		sessionStorage.setItem('message',str);
	}
	function loadStorage(id){
		var target = document.getElementById(id);
		var msg = sessionStorage.getItem('message');
		target.innerHTML = msg;
	}
###localStorage模式script.js文件如下：		
	//localStirage 永久存储
	function saveStorage(id){
		var target = document.getElementById(id);
		var str = target.value;
		localStorage.setItem('message',str);
	}
	function loadStorage(id){
		var target = document.getElementById(id);
		var msg = localStorage.getItem('message');
		target.innerHTML = msg;
	}

