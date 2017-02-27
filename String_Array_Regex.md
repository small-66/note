#字符串、数组、正则表达式
	
##1、字符串方法
*	### indexOf(str,number)
	*	查找字符串（str）为要查找的字符串，number为从原字符串第几位开始查找）
	*	返回值为str所在字符串的下标值
	*	查找的str如果不在该字符串中时，返回值为-1
*   ### includes(str)
	*   返回值为Boolean  
	*   查找某个字符串是否含有str
*   ### startsWith(str)
	*   返回值为Boolean 
	*   查找某个字符串是否以str开头
*   ### endsWith(str)
	*  返回值为Boolean
	*  查找某个字符串是否以str结尾

*	### str.slice(start,end)
	*	截取字符串
	*	返回 str中 包含start 不包含end的字符串
	> 如果start>end 返回""空字符串
	> 如果start或者end 为负数 则从start+length 到 end+length
*	### str.substr(start,number)
	*	start 为从第几位开始  number 为截取多少位字符串
*	### str.substring(start,end)
	*	从start开始截取到end（不包含end）
	*	如果start<end 则start和end互换
*	### str.toUpperCase() 
	*	返回大写的str
*	### str.toLowerCase()
	*	返回小写的str
*	### str.split(sparator,[limit]);
	*	用来分割字符串，第一个参数为用什么来分割字符串
	*	第二个参数为可选参数，为取分割后的数组中的前几位
	*	如果sparator 为空， 则分割所有字符串
*	### str.trim();
	*	去字符串前后的空格
*	### str.charAt(number);
	*	返回指定索引位置的字符
*	### str.concat(str1);
	*	连接两个或多个字符串，返回连接后的字符串	
*	### str.replace(str2,str1);
	*	返回 str1替换str2在str匹配的字符串
****
##2、数组Array

###创造数组的方法 
	var arr = new Array(1,2,3)
		arr---> [1,2,3]
	var arr = Array.of(1);
		arr---> [1]
	var arr = new Array(3);
		arr---> ['','',''];

>new Array(x); <br/>参数x为一个的时候,创建长度为参数x内容为undefined的数组 
###判断是否为数组的方法：
*	### Array.isArray(arr);
	*	返回值为boolean值 
### 把一个类数组转换成数组的方法：
*	### Array.from(str);
	*	把一个类数组 转换为数组（目前不兼容)

###数组的其他方法：
*	### arr.indexOf(x,num);
	*	与字符串方法类似，返回x所在索引 num为从第几位查找
	*	未找到后 返回-1
*	### arr.push(l1,l2...);
	*	向数组最后添加l1,l2....
	*	返回值为数组长度
*	### arr.unshift(l1,l2...);
	*	向数组最前面添加l1,l2....
	*	返回值为数组长度
*	### arr.shift()；
	*	删除第一个
*	### arr.pop();
	*	删除最后一个
*	返回值 为删除的数据
*	### arr.slice(start,end);
	*	可提取字符串的某个部分，并以新的字符串返回被提取的部分。
*	### arr.splice(start,nub);
	*	删除从start开始的nub个数据
	*	返回被删除的数据
*	### arr.splice(start,nub，x);
	*	删除从start开始的nub个数据 后在start的位置添加x
	*	返回被删除的数据
*   ### arr.reverse();
	*  颠倒数组的位置
*	### arr.forEach(function(item,i,arr){});
	*	循环数组arr item表示数组的每一个，i表示数组下标
*	### arr.map(fn);
	*	有返回值
*	### arr.fill(str,start,end)
	*	填充数组
*	### arr.join();
	*	数组转成字符串，有一可选参数，  
	*	没有参数时  由数组中“，”连接字符串  ；
	*	有参数，用参数连接字符串
*	###arr.sort();
	*	按asc码排序
	*	从大到小、从小到大
			
			arr.sort(function(a,b){
				return a-b;//从小到大排序
				return b-a;//从大到小排序
			});
	* 随机排序
		 
			arr.sort(function(){
				retrun 0.5-Math.random();//随记排序
			})

***
##3、正则表达式
### &&正则表达式是由一个字符序列形成的搜索模式。<br/>当你在文本中搜索数据时，你可以用搜索模式来描述你要查询的内容。<br/>正则表达式可以是一个简单的字符，或一个更复杂的模式。<br/>正则表达式可用于所有文本搜索和文本替换的操<br/> 查找匹配某些符合规则的字符串
*  简写：/规则/
*  new RegExp(字符串规则，修饰符）
	* 修饰符 ：
	<br/>      g-->global 全局   /s/g 
	<br/>	   i--> 忽略大小写	
*	^如果在正则的开头写 ：为开头的意思
*	$在正则结束的位置写：为结尾
			
			[] 表示一定范围 [1-5] 表示1到5的数字
		 	^ 在开头表示开头   
		 	如果[]+^ 表示排除
		 	\d 一个数字
		 	\D
		 	\s 转义字符  表示空格
		 	\S 非空格
		 	\w 数字 字母 下划线
		 	\W




###方法：
*	### test 查看正则表达式 与指定字符串 是否匹配
	*	/s/.test(str) 
*	### match 将匹配到的正则放进数组中
	*	str.match(/s/)
*	### search 找到字符串中指定字符的位置 没有返回-1
	*	str.search(/s/)
*	replace 替换
	*	str.replace(/s/,'str');


>###将不同格式的时间 转义到一个相同样式
		var dates='2016/年+/---11+月28日+';
		var arr= dates.match(/\d+/g).join('-');
		console.log(arr);
		var s=dates.replace(/(\d+)\D+(\d+)\D+(\d+)\D+/,function($0,$1,$2,$3){
			return $1+'年'+$2+'月'+$3+'日';
		})
		console.log(s);