---
layout:     post
title:      "饿了么的 PWA 升级实践"
subtitle:   "Upgrading Ele.me to Progressive Web App"
date:       2017-07-12 12:00:00
author:     "Hux"
header-img: "img/in-post/post-eleme-pwa/eleme-at-io.jpg"
header-mask: 0.3
catalog:    true
tags:
    - 前端开发
    - JavaScript
    - PWA
---


> 很荣幸在今年 2 月到 5 月的时间里，以顾问的身份加入饿了么，参与 PWA 的相关工作。这篇文章其实最初是在以英文写作发表在 medium 上的：[Upgrading Ele.me to Progressive Web Apps](https://medium.com/elemefe/upgrading-ele-me-to-progressive-web-app-2a446832e509)，获得了一定的关注。所以也决定改写为中文版本再次分享出来，希望能对你有所帮助 ;) <br><br>
> 本文首发于 [CSDN](http://geek.csdn.net/news/detail/210535) 与《程序员》2017 年 7 月刊，同步发布于 [饿了么前端 - 知乎专栏](https://zhuanlan.zhihu.com/ElemeFE)、[Hux Blog](https://huangxuan.me)，转载请保留链接。

<div>
  ###  **项目介绍** 
项目大概完成了商城后台，小程序所有页面和功能，wap的部分功能

面向学习型的开源框架，简洁高效，减少过渡封装，展现技术本质

Springboot作为容器，使用mybatis作为持久层框架

使用官方推荐的thymeleaf做为模板引擎，shiro作为安全框架,主流技术，“一网打尽”

基于注解的sql写法，零XML，极简配置，一键前后台代码生成

###  **功能简介** 


1. 用户管理
2. 角色管理
3. 部门管理
4. 菜单管理
5. 系统日志
6. 代码生成
7.内容管理

商城模块 （店铺管理，商品管理，类别管理，地址管理，专题管理，文章管理，banner管理，优惠劵管理，品牌管理，
购物车管理，评论管理，我的收藏，楼层管理，分类管理，会员管理，订单管理 ，订单日志）

###  **所用框架** 


  前端 
1. Bootstrap
2. jQuery
3. bootstrap-table
4. layer
5. jsTree 

后端
1. SpringBoot 
2. MyBatis
3. Thymeleaf
4. Shiro

1.项目部署，将bootdo.sql导入mysql，修改application-dev.yml文件的数据库信息，
运行bootdo模块的 BootdoApplication类（直接点右键运行）
http://localhost/login 后台  账号 admin admin
http://localhost/taobao/login  wap项目   账号 456789  456789

2.创建小程序的账号，下载开发工具，然后导入项目webchatapp
打开shell或cmd，进入ngrok目录，运行 `ngrok -config ngrok.cfg -subdomain zscat 80`
然后运行小程序
### 接口.md为 小程序的接口

### 后台商城演示

![输入图片说明](https://gitee.com/uploads/images/2017/1025/180334_51525b54_134431.png "QQ图片20171025174621.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180346_f53edd7c_134431.png "QQ图片20171025174635.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180355_eb20b1b5_134431.png "QQ图片20171025174645.png")

### h5演示

![输入图片说明](https://gitee.com/uploads/images/2017/1025/180412_b9755dfe_134431.png "QQ图片20171025174652.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180420_94e11148_134431.png "QQ图片20171025174658.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180432_b9f7b2b6_134431.png "QQ图片20171025174707.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180440_833cce1d_134431.png "QQ图片20171025174756.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180448_5c483b2a_134431.png "QQ图片20171025174801.png")

### 小程序演示

![输入图片说明](https://gitee.com/uploads/images/2017/1025/180507_0a581be2_134431.png "QQ图片20171025175709.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180516_4d0e4ba6_134431.png "QQ图片20171025175447.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180524_8d557d35_134431.png "QQ图片20171025175453.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180532_961500d0_134431.png "QQ图片20171025175458.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180541_cd4ec06c_134431.png "QQ图片20171025175512.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180550_47dad79b_134431.png "QQ图片20171025175517.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180604_3e71fb1b_134431.png "QQ图片20171025175525.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180611_544d1da3_134431.png "QQ图片20171025175552.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180619_ba8b1747_134431.png "QQ图片20171025175559.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180626_5a8cad93_134431.png "QQ图片20171025175603.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180634_c2b59ea8_134431.png "QQ图片20171025175612.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1025/180643_55227726_134431.png "QQ图片20171025175620.png")




</div>
