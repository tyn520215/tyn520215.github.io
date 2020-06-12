## Welcome to my blog  ----GakkiXIaoT
# 工作小记
##  2017-04-18
    *  昨天把jq升级到了最新版本，于是代码各种插件报错（jquery的dialog，还有些日历控件等等），查看jquery-issues发现jq发布了帮你向下兼容低版本插件* [jquery-migrate](https://github.com/jquery/jquery/issues/3157) 
 ## 2017-05-08
    学习redux+react-redux中踩到的坑：<br/>
    1.readux里reducer,state必须是对象，如果不是对象就会报错<br/>
    2.运用react-redux里的concat方法时将mapStateToProps里设置的参数作为props传给组件，再将mapStateToProps里的参数传给子组件时，由于子组件首字母没大写，导致值没有传递到子组件里
 ## 2017-06-02
    学习vue+vuex中踩到的坑：<br/>
    vuex中commit一个 mutation时第一个参数必须是string类型
 ## 2017-07-07
    公司H5页面开发过程中遇到一个只有ios有的问题，ios会把数字识别成电话号码并添加了个背景 
   ![meizhi](app.png)<br/>
   只需要在页面中添加一个meat标签禁止ios识别为电话号码
   &lt;meta name=&quot;format-detection&quot; content=&quot;telephone=no&quot; /&gt;
## 2017-07-12
   今天写vue遇到个js中引用图片的问题.<br/>
  如果直接(../image/a.png)这样引用，它无法被url-loader解析到，页面会找不到图片404。<br/>
  我使用的是vue-cli脚手架初始化的项目，<br/>
  解决方法就是把图片放到同级的static目录下直接(/static/a.png)引用就行了
## 2017-10-16
  关于vue-cli跨域问题配置proxyTable<br/>
  proxyTable: {<br/>
      '/api': {<br/>
        target: 'http://gakki318.com',<br/>
        changeOrigin: true<br/>
      }<br/>
    }<br/>
## 2018-05-07
今天处理ios网页遇到两个问题：
1.js处理时间显示NAN，解决办法需要把时间字符串进行处理一下 replace(/\-/g, "/")
2.ios键盘默认唤起数字键盘需要在input标签上添加pattern="[0-9]*"这个属性
# react练习
## * [Gmeizhi](https://github.com/tyn520215/Gmeizhi)
刚刚开始学习react一个练手项目<br/>

![meizhi](11.png)
![meizhi](22.png)<br/>
本项目运用了：<br/>
1.es6<br/>
2.react-router@4.0<br/>
3.Waterfall瀑布流react插件(PS:由于我接口的数据跟这个插件要求的数据结构不一样，所以稍微改了下这个插件)<br/>
4.react-bootstrap<br/>
5.webpack<br/>
## 感谢
* [妹纸.gank.io](https://github.com/drakeet/Meizhi)提供的妹纸接口


# vue+vuex+vue-router+vue-cli
## * [管理系统](https://github.com/tyn520215/vue-mange)
学习vue+vuex的写的一个项目
![meizhi](shwo.gif)
![meizhi](add.gif)<br/>

本项目运用了：<br/>
1.es6<br/>
2.element-ui(饿了吗前端推出的专注pc端的ui框架)<br/>
3vue+vuex+vue-router+vue-cli(脚手架)<br/>
5.webpack<br/>

## 2020-06-12
关于ios微信内置浏览器底部导航条会遮挡住页面的问题
解决方法：
在一进入页面一开始就往历史站中添加一条历史记录，唤起导航条。
先判断是不是ios,然后往history添加一条记录
let isIOS= !!navigator.userAgent.match(/\(i[^;]+;( U;)? CPU.+Mac OS X/);
if(isIOS){
    window.history.pushState({}, "title", "#");
 }
