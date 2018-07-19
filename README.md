# OneM
**OneM是一款纯ReactNative打造的集杂志浏览、音乐播放、视频播放于一体的综合性App,并且支持iOS和Android双平台**

# 请注意
* 如果有同学发现运行项目报如下错误，请将OneM项目中的react-native版本从之前的0.47.2 升级到0.49.3 执行命令：npm install react-native@0.49.3 --save

![error](http://ovyjkveav.bkt.clouddn.com/17-11-8/13256931.jpg)

* 安卓运行项目报如下错误，请开启Android模拟器的调试模式试试。

![error](http://ovyjkveav.bkt.clouddn.com/17-11-16/91256214.jpg)

* 由于虾米音乐接口更新，音乐播放器页面暂时请求不到虾米数据，近两天修复此问题
* 如果还是报错不能运行项目，请联系作者，加入作者RN交流群：620792950 告知作者即可

# 项目完整的功能讲解详情请参照作者简书
[http://www.jianshu.com/p/c8ce256db5cf](http://www.jianshu.com/p/c8ce256db5cf)

# 目录
* [项目简介](#项目简介)
* [主要功能](#主要功能)
* [效果图预览](#效果图预览)
* [安装调试](#安装调试)
* [数据API](#数据API)
* [技术要点](#技术要点)
* [使用到的常用三方库](#使用到的常用三方库)
* [实战开发中遇到的坑](#实战开发中遇到的坑)
* [后续待完成事项](#后续待完成事项)
* [待优化bug](#待优化bug)
* [总结](#总结)

# 项目简介
OneM是一款纯ReactNative开发的APP，也是作者开发的第三个RN项目，前两个项目是公司企业线上项目，OneM是作者独立开发的第一个RN开源项目。此项目框架搭建完全按照企业级项目框架标准搭建而成，开发时长约1个多月，后期也会长期迭代更新维护。项目目前支持iOS和Android双平台。iOS支持最低版本为：8.0，Android支持最低版本为：4.1。

# 主要功能
**项目功能主要包括四大模块：**

* 电影
	* 热映中、即将上映电影列表
	* 电影详情
	* 电影预告片、花絮、照片墙列表
	* 电影播放器，仿爱奇艺视频播放器页面，支持横竖屏切换
* 音乐模块
	* 音乐列表
	* 音乐详情
	* 音乐播放器，仿网易音乐播放器页面，支持播放模式切换
* 图文模块
	* 图文杂志列表
	* 图文详情
	* 图文栅格列表页
* 阅读模块
	* 阅读文章列表
	* 阅读分类
	* 阅读详情
	* 阅读评论
* 我的
	* 个人中心页面
	* 账号登录页面
	* 三方平台授权登录
	* 注册页面
	* 项目中使用的常用技术的Demo集合页面

# 预览效果图
![gif](http://ovyjkveav.bkt.clouddn.com/17-11-7/92017297.jpg)

# 查看更多效果图
**[https://github.com/guangqiang-liu/OneM-preview](https://github.com/guangqiang-liu/OneM-preview)**

# 安装调试
1. `git clone https://github.com/guangqiang-liu/OneM`
2. `npm install -g react-native-cli`（*如果之前安装过全局的react-native-cli请忽略此步骤*）
3. `react-native link`
4. `npm install`
5. `npm start`
6. 使用Xcode 或者Android Studio 运行项目

# 数据API
**项目中使用到的数据来源于网络抓包，在此也感谢前人总结的API文档**

[ONEM：https://github.com/guangqiang-liu/OneM-API](https://github.com/guangqiang-liu/OneM-API)

# 技术要点
* 使用react-native-router-flux与Redux结合搭建项目框架
* 项目中数据管理基于Redux框架全局Store管理
* 项目支持iconFont字体以及支持自定义font库
* 项目中接入蚂蚁金服ant-design-mobile组件库
* 封装了一套基于react-native-router-flux框架的AOP打点框架
* 自定义网络请求框架以及数据缓存策略
* 支持同时适配iOS、Android样式，自定义styleSheet组件
* iOS支持自动管理键盘弹出遮挡问题
* 集成友盟三方分享和授权登录
* 封装音频播放器组件，UI效果完全按照网易音乐播放器界面打造
* 封装视频播放器组件，UI效果完全按照爱奇艺视频播放器界面打造
* 自定义debug面板，App中便捷切换各种开发环境和随时查看当前发送的网络请求列表和对应的请求数据
* 自定义表单请求参数校验器Validate组件
* 封装了一套强大完善的Form表单组件
* 待补充

# 使用到的常用三方库
* antd-mobile
* react-dom
* react-native-blur // 原生依赖库
* react-native-button
* react-native-device-info // 原生依赖库
* react-native-image-zoom-viewer
* react-native-message-bar
* react-native-orientation // 原生依赖库
* react-native-progress
* react-native-root-siblings
* react-native-root-toast
* react-native-router-flux
* react-native-scrollable-tab-view
* react-native-simple-store
* react-native-storage
* react-native-swiper
* react-native-tab-navigator
* react-native-vector-icons  // 原生依赖库
* react-native-video // 原生依赖库
* react-native-viewpager
* react-native-zoom-image
* react-timer-mixin
* react-navigation
* react-redux
* Redux
* redux-actions
* redux-promise-middleware
* redux-thunk
* 待补充

# 实战开发中遇到的坑
* Android编译报错：Error:Could not add entry '-6081986774160961524' to cache fileSnapshots.bin (/Users/guangqiang/Desktop/ProjectRepo/ReactNative/OneM/android/.gradle/2.14.1/taskArtifacts/fileSnapshots.bin)
* 接入iconFont组件库，安卓工程报错
![errorImg](http://ovyjkveav.bkt.clouddn.com/17-10-27/55829900.jpg)
**解决方案：[http://www.jianshu.com/p/9f6db8e38852](http://www.jianshu.com/p/9f6db8e38852)**
* `Actions.xxx({type: 'xxx'})`: router-flux路由跳转页面传递参数时，参数属性名不能为`type`，否则无法正常跳转页面

* ReactNative报错: unddefined is not an object（evaluating ‘_react2.PropTypes.xxx’）
![errorImg](http://ovyjkveav.bkt.clouddn.com/17-10-27/96143070.jpg)

**解决方案：[http://www.jianshu.com/p/16a8f2d63ab3](http://www.jianshu.com/p/16a8f2d63ab3)**

* RN项目在iOS端导出ipa是报：Can't find 'node' binary to build React Native bundle

![errorImg](http://ovyjkveav.bkt.clouddn.com/17-11-5/27889340.jpg)
**解决方案：[http://www.jianshu.com/p/4501ed597aba](http://www.jianshu.com/p/4501ed597aba)**

* 待补充

# 后续待完成事项
- [x] 网络缓存
- [ ] 自定义debug面板
- [ ] 日志打点视图
- [x] Form表单组件
- [x] Validator参数校验器组件
- [ ] iOS项目支持pod
- [x] 三方分享功能
- [x] 三方登录功能
- [ ] 文件上传与下载
- [ ] 优化代码，修改bug
- [ ] 待补充

# 待优化bug
- [ ] 音乐播放器CD盘旋转问题
- [x] 音乐播放器自动切换不播放音乐问题
- [x] 自定义组件库适配问题
- [x] reading列表数据文章内容当返回html代码时，页面滑动问题
- [ ] 待补充

# 总结
**OneM项目是基本完全按照公司企业开发的要求和标准来搭建整体框架和开发的，非常适合RN初学者和有一定RN开发基础的同学们参考学习。希望OneM能给同学们带来不一样的收获。如果同学们在开发中遇到RN的问题，也可以加入作者的RN技术交流群，多多提问、交流(QQ交流群：620792950)。**

**当然，如果同学们认为作者的开源项目还不错，也请给个 `star` 支持一下 🙏🙏🙏 。也衷心的欢迎同学们给作者提些宝贵的意见和建议！**

GIT ADD!
GIT ADD! --AMEND
GIT ADD! --AMEND repeat
