---
title: 珠峰架构课目录-leesir
date: 2021-10-13 22:31:56
tags: 珠峰架构课目录第二版 姜文 张仁阳
---

> ### 一、珠峰高级全栈架构课基础部分
1. ES6/ES7语法和原理实现
2. 异步发展过程：callback、promise、generator、co、async/await等异步流程控制(async和await的实现原理) 
3. promise设计模式原理及在es6中的应用，手写一个符合promise A+规范的promise实现 
4. Node基础与实战 
5. Node事件原理和发布定阅设计模式 
6. 函数式编程 

> ### 二、模块化的演进
1. JavaScript模块化发展的演进历史 CommonJS、AMD、CMD、ES6模块的演进历史
2. 目前最主流的模块化实现方案: CommonJS 到 ES Module
3. 手写 CommonJS 的简单实现

> ### 三、前端工程化构建工具
1. gulp的基本用法以及实现原理 
2. 常用插件(压缩、合并、编译、预览服务、自动注入) 
3. node.js中自定义流的高级用法 
4. 实现自定义插件(auto-prefixer) 
5. webpack基本用法以及运行原理 
6. 常见的loader以及plugin(DllPlugin等) 
7. Webpack工作原理分析 
8. 编写自定义Loader、编写自定义Plugin 
9. webpack优化(resolve、模块热替换、压缩、代码分割、可视化工具)

 > ### 四.React全家桶

  #### 1.react基础

1. 为什么采用组件化的方式
2. react环境搭建
3. JSX语法的使用(createElement,render的原理实现)
4. JSX表达式的用法
5. JSX的属性(className,htmlFor,style,dangerouslyInnerHTML)
6. 组件使用(类声明,函数声明)
7. 组件的属性和状态(属性的检验以及setState详解)
8. 复合组件
9. 组件的声明周期
10. 受控组件 非受控组件
11. children属性的使用
12. 项目实战留言板

  #### 2.redux
1. 手写redux库(getState,createStore,dispatch,subscribe,applyMiddlewar e,combineReducer,compose,bindActionCreators)

  #### 3.react­redux
1. 高阶组件的原理和使用
2. react高级属性context上下文
3. react-redux实现todoList
4. 手写react-redux(Provider和connect原理解析)

  #### 4.中间件
1. 手写applyMiddle和compose(中间件原理)
2. 手写redux-logger,redux-thunk,redux-promise
3. 手写自定义本地缓存中间件

  #### 5.react­router­dom
1. HashRouter,BrowserRouter的区别
2. Link,NavLink的使用(extact绝对匹配,state带参数跳转)
3. Route组件三种渲染方式(component,render,children)
4. 路由参数以及子路由的使用(params)
5. withRouter,PrivateRouter的用法
6. Prompt组件阻止跳转
7. 重定向(Redirect组件)
8. 手写HashRouter Route等常用组件

  #### 6.React­Transition­group
1. react动画的实现原理 2.使用React-Transition-group库开发todo动画应用

  #### 7.项目实战React珠峰课堂1.0项目
  #### 8.源码级Vue+React深度解析与实现
1. 手写Vue双向绑定实现
2. Vue虚拟DOM和React虚拟DOM的区别
3. 如何实现一个 Virtual DOM 算法
4. 通过源码彻底搞明白setState的更新机制
5. 手写包含虚拟DOM、事件监听、基本组件生命周期等功能的React库

  ### 五.node高级
  #### 1.http深入和tcp详解
  #### 2.express
1. 手写express框架
2. 中间件的实现原理、bodyParser、cookie-parser、static、模板原理

#### 3.Koa
1. 手写Koa框
2. 中间件的实现原理、bodyParser、cookie-parser、static、模板原理

  #### 4.Linux
  #### 5.Mongodb
  #### 6.珠峰博客(express+mongodb+mongodb)
  基于bootstrap+express+mongodb实现一个包括用户管理、文章管理、多看留言、分页查询、 搜索、文件上传、pv留言统计等功能完整的博客系统。使用了express的路由、ejs模板和serve-favicon、morgan、cookie-parser、body-parser、express-session、connect-mongo、connect-flash、uuid、async等内置各种中间件以及其它发路径保护等自定义中间件，并扩展了富文本编辑器、markdown和heroku云布署等功能。

  #### 7.珠峰聊天室项目实战(react+socket.io+mongodb)
  #### 8.MySQL
  #### 9.珠峰爬虫(cheerio+request+mysql)
  #### 10.Redis
  #### 11.Nginx
  #### 12.Docker
  #### 13.单元测试
  #### 14.集群和负载均衡
  #### 15.前端性能监控与性能优化、行为监控与安全防范
  #### 16.项目部署
  #### 17.安全
  #### 18.功能测试与性能测试
  #### 19.全链路优化
  ### 六、前端设计模式(选讲)
  #### 创建型设计模式
  #### 结构型设计模式
  #### 行为型设计模式

  ### 七、算法&数据结构(选讲)
1. 时间复杂度
2. 空间复杂度
3. 常见排序算法
1. 冒泡排序、优化
2. 选择排序
3. 插入排序
4. 归并排序
5. 快速排序式
6. 计数排序
7. 桶排序
8. 基数排序
4. 链表(链表反转、链表是否有环)
5. 树(高度、前序、中序、后序、广度优先算法、反转)
6. 二叉树搜索算法
7. 青蛙跳台阶问题动态规划算法
8. React虚拟DOM Diff算法实现
