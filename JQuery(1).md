#JQuery内容
***
###1、$()选择器
####   $('.className') 、$('#id') 、$('targName) 来直接选择元素
		<body>
	        <div id="div1" class="box">div</div>
	        <!-- <div class="box">div</div> -->
	        <script>
	            var a = $('#div1');
	            // console.log(a)
	            a[0].style.background = '#58a';
	        </script>
	    </body>
#
		<body>
	        <ul>
	            <li></li>
	            <li class="target"></li>
	            <li></li>
	            <li></li>
	            <li></li>
	        </ul>
	        <script>
	            var a = $('ul li');
	            console.log(a)
	        </script>
	    </body>
>注： 1. 通过$()获取的是一组数据，在使用时必须配合下标；<br/>
      2. $()功能相当于querySelectorAll()

###2、具有独有的表达形式 

		<ul>
	        <li></li>
	        <li class="target"></li>
	        <li></li>
	        <li></li>
	        <li></li>
	    </ul>
	    <script>
	        var a = $('li:first')
	        a[0].style.background = 'red';
	
	        var b = $('li:eq(2)')
	        b[0].style.background = '#58a';
	
	        var c = $('li:odd')
	        for (var i = 0; i < c.length; i++) {
	            c[i].style.background = 'blue';
	        }
	
	        var d = $('li:even')
	        for (var i = 0; i < d.length; i++) {
	            d[i].style.background = 'yellow';
	        }
	    </script>
	
