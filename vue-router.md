##vue-router

###1、安装依赖  
	cnpm install vue-router --save

###2、在入口文件中引入（main.js)

	import VRouter from 'vue-router'

使用use方法使用

	Vue.use(VRouter)

使用路由的时候 
	
	let router = new VRouter({
		mode : 'history',
		routes :[
			{
				path:'/',
				redirect: '/apple'
				/*
				(重定向:在访问根目录时 重定向访问到apple页面)
				*/
			},
			{
				path:'/apple',
				components: Apple
			}
		]
	})
>routes 数组里存映射表
>mode:'history' H5中history功能
>Apple 为组件 要引入该组件
>import Apple from '组件地址'

###在项目中使用路由时
	<router-view></router-view>
	页面里跳转
	<router-link :to="{path:'/apple'}">
		跳转到apple页面
	</router-link>
	<router-link to="apple">
		基于当前路径跳转到apple页面
		（如果要跳转到根目录下apple  要写/apple）
	</router-link>
	<router-link :to="'apple'">
		基于当前路径跳转到apple页面
		（如果要跳转到根目录下apple  要写/apple）
	</router-link>

###前端路由参数
在映射表里 

		{
			path:'/apple/:color',
			components: Apple
		}
在每个子组件里 通过this.$router.params来获取当前路由的参数

###嵌套路由

	{
		path:'/apple',
		components: Apple，
		children: [
			{
				path:'red',
				components: RedApple
			}
		]
	}
在Apple组件里 添加<router-view></router-view>

###将router-link 指定为li
	<router-link :to="'apple'"  teg="li">
		基于当前路径跳转到apple页面
		（如果要跳转到根目录下apple  要写/apple）
	</router-link>	

###编程式导航router.push({path:''})

###命名路由
	{
		path:'/apple/:color',
		name: 'ApplePage',
		components: Apple
	}
###命名视图
	<router-view name="viewA"></router-view>
	<router-view name="viewB"></router-view>
	
	{
		path:'/apple/:color',
		components: {
			viewA: Apple,
			viewB: RedApple
		}
	}
	
###过渡

	<transition name="fade">
		<keep-alive>(缓存)
			<router-view></router-view>
		</keep-alive>
	</transition>
