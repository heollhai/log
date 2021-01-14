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
##  如果选择了  lint
 1.  ESlint + prettier    //prettier用来格式化代码用的
 2.  Lint on save
 3.  In dedicated config files


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

