#Bootstrap
##

#1 bootstrap栅格系统
###概念：
#####分12列 (页面被分成12个网格，即一行12个)
>row<br>
>col
#####阈值  (对应下面容器的固定布局的宽度)
>1200>= 语法： col-lg-1  <br>
>992>=  语法： col-md-1  <br>
>768>=  语法： col-sm-1  <br>
>768>   语法： col-xs-1  <br>

###容器（class为以下两种）
>container-fluid 流体布局<br>
>container 固定布局(1170  970 750 auto)

PS: 做容器的时候 因为存在padding值 一个页面可以有一个容器或者多个容器 但不要嵌套

###组合模式 
.class="col-lg-1 col-md-1 col-sm-1 col-xs-1"

###列偏移
class="col-lg-offset-2" 
<br>列偏移时 如果一行多个div超出12则另起一行后进行偏移
###列排序
col-lg-push-2   ===>向右偏移2个栅格
col-lg-pull-2   ===>向左偏移2个栅格
###浮动
pull-left pull-right
###清除浮动
在要清除浮动的元素前加一个
    
    <div class="clearfix"></div>

###响应式工具
针对不同设备展开或者隐藏页面的内容<br>
	1.可见类:
		~1、visible-md-block 
			在md情况下显示
	<br>~2、hidden-sm
			在sm情况下隐藏
	<br>2.打印类（visible-print-block  hidden-print）

###固定定位  affix
###字体图标 Glyphicons
用法：引入fonts目录文件夹

		<span class="glyphicon glyphicon-search"></span>

>注：fonts文件夹位置路径在bootstrap.css里font-face里设置修改

###预定义样式风格

		primary      首选项
		success      成功
		info         一般信息
		warning      警告
		danger       危险
	可用在：bg-   btn-   text-  等
	<input type="button" value="首选项" class="btn btn-primary"/>