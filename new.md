##	一、账号，密码
##	二、git 
##	三、css3动画效果、媒体查询
##	四 、项目常用单词（Utils，转换，拷贝，flex，继承）
##	五、下载依赖
##	六、路由跳转：
##	七、引入Swiper
##	八、axios封装
##	九、vue-baidu-map控件总结(控件名)
##	十、vue自定义指令
##	十一、路由守卫
##	十二、watch监听事件
##	十三、子组件使用父组件(方法)和更改父组件(data)里面的值
##	十四、页面刷新
##	十五、vue使用百度地图
##	十六、常用的修饰符:
##	十七、vue项目导出excel表格
##	十八、css样式层级
##	十九、捕获，冒泡
##	二十、set的使用
##	二十一、判断是数组还是对象

## 常用方法:
##   height: 100vh;     // vh是屏幕高度
##   element ui 一般使用的3中大小尺寸 : medium / small / mini
## 高度设置自适应其中一种方式 height: 'calc(100% - 20px)'//高100%在少20px
## box-shadow: 10px 10px 5px #888888;  阴影效果
## 超出显示三个点：
		overflow: hidden;white-space: nowrap;text-overflow: ellipsis;
## 调出打印     window.print();
## 鼠标放上效果  cursor: default;//放上正常效果  cursor:pointer //鼠标方法手的形状;

##	一、账号，密码
	github: 账号：heollhai			密码：	a4311281997
	xiaod:		1768827067						a4881351	

##	二、git
	1、git 上传：
		1.1、进入项目地址，通过命令git init将项目初始化成git本地仓库
		git init  
		1.2、将项目内所有文件都添加到暂存区
		git add .
		1.3、该命令会将git add .存入暂存区修改内容提交至本地仓库中，若文件未添加至暂存区，则提交时不会提交任何修改。
		git commit -m 'xxx'   //xxx是备注名
		1.4、在github上新建一个仓库，复制仓库地址，然后使用命令将本地仓库与远程仓库建立连接
		（4.1）git remote add origin  xxx       //xxx是git仓库的地址
		（4.2）4.1这个步骤可能出现错误 提示fatal: remote origin already exists
		执行：git remote rm origin命令
		（4.3）再执行（4.1）的命令
		1.5、把暂存区的代码推到远程仓库
		git push -u origin master
	2、创建分支，克隆，解决冲突：
		git  checkout  分支名  
		然后需要提交分支上github上本地才能正常装换     提交去看   git提交笔记  
		克隆
		git clone xxx.git --branch 分支名/dev/...     git下载指定分支
		克隆所有
		git clone （地址）
	3、git 拉取github上分支代码
	  1. 自己要与origin master建立连接（下划线为远程仓库链接）
		git remote add origin git@github.com:XXXX/nothing2.git
	  2. 把远程分支拉到本地
		git fetch origin dev（dev为远程仓库的分支名）
	  3. 在本地创建分支dev并切换到该分支
		git checkout -b dev(本地分支名称) origin/dev(远程分支名称)
	  4. 把某个分支上的内容都拉取到本地
		git pull origin dev(远程分支名称)
	4、add，commit后，，，版本回退
		1.输入命令查看本地记录git reflog					-------		输入命令查看本地记录
		2.找到本次rebase之前的id
		3.执行命令回退 git reset --hard ca606c6			-------		回退到以前版本	ca606c6   是版本还号	
		4.执行命名取消rebase状态 git rebase --abort      -------   	回到以前提交但没有pull是的状态
	4、常用命令
		git init 初始化
		git clone 克隆代码库
		git clone -b dev(dev是分支名称s) 克隆代码库
		git config 配置
		git add 增加文件到暂存区
		git commit 提交暂存区到仓库
		git branch 名称  新建分支
		git checkout 切换分支
		git merge 合并分支
		git branch -d 删除分支
		git tag 打tag 包
		git status 查看状态
		git log  查看日志
		git diff 查看暂存区和工作区差异
		git fetch  下载远程仓库的变动
		git pull 取回远程仓库变化，并与本地分支合并
		git push 上传本地指定分支到远程仓库
		git reset --merge		取消合并
		git reset --hard ca606c6	回退到以前版本
		git rebase --abort			回到以前提交但没有pull时状态
		git reflog					查看本地记录
sss##	三、css3动画效果
	Css3的几种动画
	1、transform转变动画
		transform:rotate(3deg)//旋转3deg
		transform-origin:20% 40%;//设置旋转元素基点
		transform-style: preserve-3d;//实现3d效果，具体使用查一下（不常用）
	2、animation自定义动画
		1、mymove(动画名)    from（开始）  to（结束 ）
		先定义动画：  
		 @-webkit-keyframes mymove 
		{
			from {left:140px;top:212px;width:0;height:0;}
			
			to {left:44px;top:133px;width:186px;height:180px;
				transform: rotate(1800deg);
				transform:translate  //平移
				scale（缩放）、skew（拉伸）
			}
		}
	使用：
		.bb{
			background:red;
			position:relative;
			animation:mymove 3s; //代表动作3秒完成
			animation-fill-mode:forwards;//代表动作移动后停在那里
			animation-duration:2s;//设置动画在两秒内完成:
			animation-direction:alternate;//先执行一遍动画，然后再反向执行一遍动画：
			animation-delay:2s;  //等待两秒，然后开始动画
			animation-iteration-count:3;//动画直行3次
			animation-iteration-count:infinite;//循环执行
		}
		
	3、Transition过度动画
	transition:2s;//2秒完成过度效果
	 
	 
	效果总结：
	linear 规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）。 
	ease 规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）。 
	ease-in 规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)）。 
	ease-out 规定以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）。 
	ease-in-out 规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）。 
	cubic-bezier(n,n,n,n) 在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值。 
	
	4、媒体查询
		body {
		    background-color:lightgreen;
		}
		
		@media screen and (max-width: 300px) {//小于300时变色
		    body {
		        background-color:lightblue;
		    }
		}

		
##	四、项目常用单词
	Utils   
	     1.   一般用来放  request.js（axios）封装
	     2.   support     对cookie的封装    （缓存）
	  
	  localStorage.setItem('cart',JSON.stringify(data));      向缓存中（cart）里面存放一个 已经转成字符串的数据
	如果没有（cart）那么会创建一个（cart）
	
	  console.log(JSON.parse(localStorage.getItem('cart')),'112')   向缓存中拿数据 
	转换:
		JSON.stringify(obj); 
		JSON.parse(_obj)
	
	拷贝:
		浅拷贝
		b=a.slice();
		b=c.concat(a);数组连接'
	
	flex 的水平居中和垂直居中
		水平：justify-content:center;
		 垂直：align-content：center;
		方向 : flex-direction
		空白环绕:
		（div左右会有一半间隙)space-around 
		空白平分:
		（div左右没有间隙） space-between
		
		排序：
		flex-direction: row | row-reverse | column | column-reverse;
		row 从左到右排列 
		row-reverse从右到左排列
		column 从上到下排列 
		column-reverse从下到上排列
	
	继承:
		Parent.apply(this,arguments)  表示  this用Parent的，，并继承那里面的内容方法
		
##	五、下载依赖
	## vue-cli 脚手架
	1.创建项目，写出一部分代码
	2.热启动，（只修改代码，浏览器上的网页会自动刷新，显示修改后的内容）
	3.有利于单元测试
	## 创建新项目的流程
	1. 先安装node
	2. 安装淘宝镜像
	npm install -g cnpm --registry=https://registry.npm.taobao.org
	
	3. 全局安装脚手架
	cnpm install -g @vue/cli
	或
	npm install -g @vue/cli
	
	4. 测试脚手架是否安装成功
	vue/cli -V   
	如果显示了版本号，则表示 脚手架安装成功
	
	5. 进入到项目目录
	
	    1. 创建项目  一般选择   可能还会有一问问是否使用淘宝镜像，，有可能没有
	    2.Manually select features   自定义选项
	    3.会询问安装那些  一般安装  Babel, Router, CSS Pre-processors  如果需要xuex   的话也要安装
	    4.vue create vue-xm
	    5.  No（Use history mode for router?提示是否使用history模式，No的话是使用哈希模式，history模式有时打包可能会有问题，，，所以选No）
	    6.选择  Sass/SCSS (with node-sass)
	    7. In package.json
	    8.Yes  （提示是否保存配置）
	    9.在输入（保存的配置名称）
	
	
	
	守卫一般创建在mian.js同层   
	取名为permission.js
	 
	
	二.依赖下载
	npm  install --save axios echarts v-charts normalize.css js-cookie element-ui 
	     1.  axios 获取数据
	     2. echarts 图表
	     3. v-charts echart和vue的结合体
	     4.normalize.css 样式重置
	     5.js-cookie cookie的使用 (Cookie 用于存储 web 页面的用户信息。)
	     6.element-ui 饿了么ui库
	     7.vuex-persistedstate'     数据持久化
	
	
	
	三，引入   写在main.js中的
	     1.import Vue from 'vue'  VUe引入
	      2.import VueRouter from 'vue-router'     路由引入
	      3.import axios from 'axios'
	Vue.prototype.$axios = axios（axios写入vue原形） 4.import'@/assets/icons/font/iconfont.css'  引入element小图标
	5.import 'normalize.css'    （样式重置）
	6.import Element from 'element-ui'
	import 'element-ui/lib/theme-chalk/index.css'
	Vue.use(Element) （element  插件使用）
	7.import VCharts from 'v-charts';
	Vue.use(VCharts); （图表）
	npm install lib-flexible --save   px转rem
	
	
	
##	六、路由跳转：
		path                       (跳转地址)
		name                   （路由名称）
		component         （组件）
		meta                     （路由元信息）
		children                （路由里面子路由）
		redirect: '/index'   （路由重定向方法1）
		redirect: {name: 'index'}（重定向方法2）
		
		this.$router.push('/home')
		//params
		this.$router.push({name:'home',params: {id:'1'}}) 
		// html 取参  $route.params.id
		// script 取参  this.$route.params.id
		-----------------------------------------------------
		//query 传参
		this.$router.push({path:'/home',query: {id:'1'}})
		// html 取参  $route.query.id
		// script 取参  this.$route.query.id
		-----------------------------------------------------
		//go方法
		this.$router.go(n)
		-----------------------------------------------------
		//路由用scss激活时改变样式
		&.router-link-exact-active     路由激活时设置的样式
		
		
		
		路由的参数获取
		 console.log(this.$route)//当前页面路由信息
		console.log(this.$route.meta)//路由元信息
		console.log(this.$router)//vue路由实例
		
		下面是路由传参详情 ：
		不带参数
		this.$router.push('/home')
		this.$router.push({name:'home'})
		this.$router.push({path:'/home'})
		-----------------------------------------------------
		//params
		this.$router.push({name:'home',params: {id:'1'}})  // 只能用 name
		// 路由配置 path: "/home/:id" 或者 path: "/home:id" ,
		// 不配置path ,第一次可请求,刷新页面id会消失
		// 配置path,刷新页面id会保留
		//query 取参
		// html 取参  $route.params.id
		// script 取参  this.$route.params.id
		-----------------------------------------------------
		//query 传参
		this.$router.push({path:'/home',query: {id:'1'}})
		this.$router.push({name:'home',query: {id:'1'}})
		// html 取参  $route.query.id
		// script 取参  this.$route.query.id
		-----------------------------------------------------
		this.$router.go(n)
		向前或者向后跳转n个页面，n可为正整数或负整数
		
		
		
		
##	七、引入Swiper
		下载
		"swiper": "^3.4.2",//这个版本能直接用
		   npm install swiper
		   
		import Swiper from 'swiper';
		 //引入swiper 的css
		 import 'swiper/swiper-bundle.css'//版本高于6.0时引入
		 低于6.0.0 import 'swiper/css/swiper.css'
		
		
		功能正常轮播图
		
		mounted:function(){
			setTimeout(()=>{
			   var mySwiper = new Swiper('.swiper-container',{
				loop:true, //循环轮播
				autoplay:2000,//自动轮播
				speed:1000,//轮播的速度
				observer:true,//异步处理数据
				observeParents:true, //异步处理数据
				pagination: '.swiper-pagination',
				paginationClickable: true
			   })
			},1000);
		}
##	八、axios封装
	
	在utils目录里面创建一个（request.js）用来封装axios
	//对axios的封装
	//引入 axios
	import axios from 'axios';
	//引入ElementUI MESSAGE
	import {Message} from 'element-ui';
	
	//创建axios的实例
	const service = axios.create({
	 baseURL:'http://10.10.10.250:8001/',//'/api/',//'http://10.10.10.250:8001/',//api的根url地址
	 timeout:1500,//数据响应的过期时间
	 //headers:{"Content-Type":"application/x-www-form-urlencoded"}//请求的文件类型的设置
	});
	
	// 添加请求拦截器， 做token的验证
	service.interceptors.request.use(function (config) {
	    // 在发送请求之前做些什么
	 /*
	 拼接 token 的值，token的验证需要后台支持；为了做后台项目时，防攻击；每次请求数据时需要设置并传递token，在后台进行验证，验证通过后，
	 服务器才会响应；如果验证不通过，后台会抱一个错误，让用户重新登录
	 */
	    return config;
	  }, function (error) {
	    // 对请求错误做些什么
	    return Promise.reject(error);
	  });
	
	// 添加响应拦截器
	service.interceptors.response.use(function (response) {
	    // 对响应数据做点什么
	 const res = response.data;//报错看一下res里面的states在哪里
	 if(res.status !== 200){
	  Message({
	   message:res.msg,
	   type:'error',
	   duration:2000
	  }) 
	 }else{
	  return response;
	 }
	 return Promise.reject('error');
	  }, function (error) {
	    // 对响应错误做点什么
	 Message({
	  message:error.msg,
	  type:'error',
	  duration:2000
	 }) 
	    return Promise.reject(error);
	  });
	  
	  //输出
	  export default service;
	  
	  在api目录中创建（product.js）
	  引入axios（拿数据实例）
	  //引入封装好的axios
	  import  request from '@/utils/request.js';
	  /*
	  设置是与后台相一致的
	  get ：传参  params
	  post :传参  data
	  */
	  //获取  get方式
	  export function fetchProductList(params){
	   return request({
	    url:'index/Api/product_list',
	    method:'get',
	    params:params
	   })
	  }
	  //获取  post方式
	  export function addprodutAttrList(data){
	   return request({
	    url:'index/Api/create_product_cate',
	    method:'post',
	    data:data
	   })
	  }
##	九、vue-baidu-map控件总结(控件名)
	地址:https://blog.csdn.net/LEVsunshine/article/details/102370448\
		常用控件功能解释: https://blog.csdn.net/qq_37346639/article/details/100104012?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param

##	十、vue自定义指令
	自定义指令钩子: //前两个常用    
		inserted: 被绑定元素插入父节点时调用（父节点存在即可调用，不必存在于 document 中）。
		update: 被绑定元素所在的模板更新时调用，而不论绑定值是否变化。通过比较更新前后的绑定值，可以忽略不必要的模板更新（详细的钩子函数参数见下）。
		bind: 只调用一次，指令第一次绑定到元素时调用，用这个钩子函数可以定义一个在绑定时执行一次的初始化动作。
		componentUpdated: 被绑定元素所在模板完成一次更新周期时调用。
		unbind: 只调用一次， 指令与元素解绑时调用。
	在elemenet里面获取焦点
		方法一:
			<el-input  v-model="form.name" v-focus autocomplete="off" type="textarea"></el-input>
			directives: {
				focus: {		
					inserted: function (el,{value}) {//类似载入是调用
						el.getElementsByTagName('textarea')[0].focus()//这个是在多行文本是使用的，，如果是type=text  那么textarea改为input
					},
					update: function (el,{value}) {//更新时候调用
						console.log(4)
						el.getElementsByTagName('textarea')[0].focus()
					}
				}
			},
		方法二:
			<el-input  v-model="form.name" v-focus:'aa' autocomplete="off" type="textarea"></el-input>
			directives: {
				focus: {		//el表示获取的节点-----value就是aa可以当做判断条件
					inserted: function (el,{value}) {
						if(value){
							el.getElementsByTagName('textarea')[0].focus()
						}
					},
				}
			},
			data(){
				aa:false
			}
##	十一、路由守卫
	vue路由守卫:
		组件独享守卫:
			beforeRouteEnter:(to,from,next)=>{ 	//使用为如果是从/discover过来的话，，那么执行 vm.shuaxin() 这个方法
				if(from.path==="/discover"){
				  next(vm =>{ //这样可以调用this    此处的vm代表this
					  vm.shuaxin()
					})
				}
				next()
			}
##	十二、watch监听事件
	https://www.cnblogs.com/yesu/p/9546458.html
	deep: true  //
	watch:{
		evnReadDialog(a,b){
			console.log(a,b)
			deep: true
		}
	},
##	十三、子组件使用父组件方法和更改父组件data里面的值
	this.$parent.$parent.$data.evnReadDialog = false;		//把父组件data里面的evnReadDialog值改为false
	this.$parent.$parent.reload();							//调用父组件里面的reload()方法
	父组件使用子组件方法
	this.$refs.child1.childMethod();						//  child1是引入子组件ref的值，，childMethod是子组件的方法
##	十四、页面刷新
	1.在app.vue里面增加一个if语句
		<router-view v-if="isRouterAlive"></router-view>
	2在app.vue里面的script里面增加
		<script>
		  export default {
		    name: 'App',
		    provide(){
		      return{
		        reload:this.reload
		      }
		    },
		    data(){
		      return {
		        isRouterAlive:true,
		      }
		    },
		    methods:{
		      reload(){
		        this.isRouterAlive = false;
		        this.$nextTick(function () {
		          this.isRouterAlive = true
				  console.log('wo刷新了')
		        });
		      },
		    },
		  }
		</script>
	3.在要刷新的页面里面添加
		inject: ['reload'],				//名字和methods里面的方法名字一样
	4.在要刷新的页面的方法里面添加 this.reload();这个方法 ---------此方法不能添加到	mounted 、created 里面不然会一直刷新
		datass(){
			this.reload();
		},
##	十五、vue使用百度地图
	一些功能解释:
		
		https://blog.csdn.net/xr510002594/article/details/84108882?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param

##	十六、常用的修饰符:
  1. 	.number; 	自动将用户的输入值转为数值类型;
  2. 	.trim;		过滤用户输入的首尾空白字符
  3. 	.stop;		阻止单击事件继续传播;
  4. 	.once;		只会触发一次;
  5. 	.enter;		回车键;
  6. 	.native		绑定组件的事件;
  7. 	.prevent	是用来阻止默认的 
##	十七、vue项目导出excel表格
	复制e盘里面的gongneng/vue项目excel表格导出  里面的两个文件 //放到项目里面的assets目录下面
	可以创建一个目录用来放置着两个文件
	项目中使用方法:
		<Button type="primary" @click="exportData" style="display:block; margin:5px auto;">导出Excel表格</Button>
		methods:{
			//触发按钮点击下载事件
			exportData() {
				this.excelData = this.historyList;  //将你要导出的数组数据（historyList）赋值给excelDate
				this.export2Excel(); //调用export2Excel函数，填写表头（clomns里的type）和对应字段(historyList里的属性名)
			},
			//表格数据写入excel
			export2Excel() {
			  var that = this;
			  require.ensure([], () => {
				const {
				  export_json_to_excel
				} = require("../../assets/js/Export2Excel");  
				//这里使用绝对路径( @表示src文件夹 )，使用@/+存放export2Excel的路径【也可以写成相对于你当前"xxx.vue"文件的相对路径，例如我的页面放在assets文件夹同级下的views文件夹下的“home.vue”里，那这里路径也可以写成"../assets/excel/Export2Excel"】
				const tHeader = ["报名日期", "姓名", "班级", "学号","性别","邮箱","联系方式","所选导师"]; // 导出的excel表头名信息
				const filterVal = [
				  "date",
				  "name",
				  "class",
				  "studentId",
				  "sex",
				  "email",
				  "telephone",
				  "teacher"
				]; // 导出的excel表头字段名，需要导出表格字段名
				const list = that.excelData;
				const data = that.formatJson(filterVal, list);
		
				export_json_to_excel(tHeader, data, "学生报名信息汇总"); // 导出的表格名称，根据需要自己命名
			  });
			},
			//格式转换，直接复制即可,不需要修改什么
			formatJson(filterVal, jsonData) {
			  return jsonData.map(v => filterVal.map(j => v[j]));
			}
		}
##	十八、css样式层级
.graph-card-main /deep/ .el-card__body {
      padding: 0 !important;    			  !important    /deep/   都是用于增加样式优先级别的
    }
	
##	十九、捕获，冒泡	
	atoolbsar.onclick = function(ev) { //点击工具栏清空工具栏子层背景颜色
	  var event=ev||window.event
	  if (event.stopPropagation) {
	    event.stopPropagation();
	  } else {
	    event.cancelBubble = true;
	  }
	  //添加这个方法在写事件，，可以解决冒泡问题
	}
##	二十、set的使用
	一 :
		  1. this.items[0] ---------	需要更改data里面的数组
		  2. message	   ---------	需要更改的数组里面的字段
		  3. 新值		   ---------	要修改成的值；
	二 :  
		  1. this.items 					---------	需要更改data里面的数组
		  2. 0	   							---------	需要更改的数组的下标
		  3. {message:'first',id:'4'}	    ---------	需要替换的数组里面的新值
  1. 	this.$set(this.items[0],"message","新值") 
  2. 	this.$set(this.items,0,{message:'first',id:'4'}) 
##	二十一、判断是数组还是对象:
   1. 	使用 instanceof		去判断		例: a instanceof Array; ------要优先判断是不是  Array   因为Array也是
   2. 	使用 constructor	判断		例: a.constructor === Array; 
   3. 	使用 prototype		判断		例: a.prototype === Array;
   4. 	使用 Array.isArray(a)