## 一、常用到的es6
## 二、keep-alive的使用
## 三、v-model 双向绑定原理
## 四、判断对象是否为空
## 五、判断对象里面某个值是否存在





## 一、常用到的 es6
   1. 	箭头函数 、let 、const 、extends  
			let 和 const  的区别  let的值可以变   const不可以;
   2. 	set 的方法：
			去重		...[new Set(arr)]
   3. 	Promise
   4. 	class:
			1.	里面有constructor方法   类似于构造函数 在constructor里面写 在super()用于继承
			2.	 static 静态的方法
			3.	 调用:
				class Point{
						static staticX = 1;
						static staticY = 1;
						constructor(x,y){
							this.x = x;
							this.y = y;
						}
						toString(){
							return this.x + "," + this.y;
						}
						static toValue(p){
							return p.x+p.y;
						}
					}
				let p = new Point(1,2);    
					let s = p.toString();      //返回"1,2"
					let val = Point.toValue(p);//返回3
					console.log(Point.staticX,Point.staticY); //输出1 1
   5. 	Symbol:
			它的值是唯一的，不可变的 	例如: 	
				var sym = Symbol( "some optional description" );
				console.log(typeof sym); // symbol
				
## keep-alive的使用
   1. include  	需要缓存的组件名		exclude 			不需要缓存的组件名
   2. activated 组件激活是调用		deactivated			页面离开时候调用
   1. 使用:
		<keep-alive> 
		        <!-- 需要缓存的视图组件 -->
		        <router-view v-if="$route.meta.keepAlive"></router-view> 
		</keep-alive>
		      <!-- 不需要缓存的视图组件 -->
		<router-view v-if="!$route.meta.keepAlive"></router-view>
		或者:
			    <keep-alive include="list">
			        <router-view></router-view> 
			     </keep-alive>
## 三、v-model 双向绑定原理
	如果使用了v-model  那么等于同时绑定了一个  input  和 value  
	
## 四、判断对象是否为空  
		let object = {}
		let object1 = {
			name:'1'
		}
	1、	if(Object.keys(object).length == 0){    
			console.log('是');
		}
	2、if(JSON.stringify(object === '{}')){}
## 五、判断对象里面某个值是否存在	
	1.	if(object1.name== undefined){			//判断值是不是等于 undefined
		console.log('是');
	}
	2.	if(Object.keys(object).indexOf(值))