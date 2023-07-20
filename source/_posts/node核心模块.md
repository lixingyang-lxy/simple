---
title: node核心模块
date: 2021-09-21 08:07:56
tags: 继承 promise events 
---

### 拷贝 继承 promisify

~~~js
// utils.js
// 拷贝 继承 promisify

// 我希望将一些模块转化成promise的方法

// yarn 其实就是npm替代品
// npm install yarn -g

// ncp 拷贝一个文件
let ncp = require('ncp');
let path = require('path');
let util = require('util');
let {inherits} = require('util');
// cp -r
const promisify = fn => (...args)=>{
    return new Promise((resolve,reject)=>{
        fn(...args,function(err){ // 只针对node  因为node是这种error-first的形式
            if(err) reject(err);
            resolve();
        });
    })
}
ncp = promisify(ncp);
(async ()=>{
    // 文件路径 path.resolve 绝对路径 文件名
    // 拷贝文件 promisify async await + 匿名函数自执行
    await ncp(path.resolve(__dirname,'note.md'),path.resolve(__dirname,'note1.md'));
    console.log('拷贝成功')
})();
// ncp(path.resolve(__dirname,'note.md'),path.resolve(__dirname,'note1.md'),(err)=>{
//     console.log(err);
// })

// inherits node内部不是用es6来写的 实现类的继承
function Parent(){

}
function Child(){
    Parent.call(this);
}   
// 只继承公共方法
Child.prototype.__proto__ = Parent.prototype;
Reflect.setPrototypeOf(Child.prototype,Parent.prototype);
Child.prototype = Object.create(Parent.prototype);

inherits(Child,Parent); // 继承公共属性
// 可以显示隐藏属性
console.log(util.inspect(Array.prototype,{showHidden:true}));
console.log(util.isPrimitive); // Symbol
~~~

### EventEmitter 发布订阅 取消订阅 一次触发 自制event事件
~~~js
// events.js
function EventEmitter(){
    this._events = Object.create(null);
}
EventEmitter.prototype.on = function(eventName,callback){
    // 不管任何人 调用了on方法 都可以增肌_events
    if(!this._events) this._events = Object.create(null);
    // 监听绑定的事件 不是newLister就调用newListener
    if(eventName !== 'newListener'){
        this.emit('newListener',eventName);
    }

    if(this._events[eventName]){
        this._events[eventName].push(callback);
    }else{
        this._events[eventName] = [callback];
    }
}
EventEmitter.prototype.once = function(eventName,callback){
    // 绑定 执行后 删除
    let one = ()=>{ // 2） 会触发one函数
        callback();// 触发原有的逻辑
        // 删除自己
        this.off(eventName,one); // 在将one删除掉
    }
    one.l = callback; // 用自定义属性 保存原有的绑定函数
    this.on(eventName,one); // 1）  先绑定
}
EventEmitter.prototype.off = function(eventName,callback){
    if(this._events[eventName]){
        this._events[eventName] = this._events[eventName].filter(fn=>{
            return fn != callback && fn.l !== callback
        })
    }
}
// {'女生失恋':[fn1,fn2]}
EventEmitter.prototype.emit= function(eventName,...args){
    if(this._events[eventName]){
        this._events[eventName].forEach(fn => fn(...args));
    }
}

module.exports = EventEmitter;

~~~

### newEvent 
~~~js
// 发布订阅模块  pub / sub
let EventEmitter = require("events");
let util = require('util');
function Girl (){
}
util.inherits(Girl,EventEmitter);
let girl = new Girl;

girl.on('newListener',(type)=>{ // 监听到用户做了哪些监听
    console.log(type)
    if(type === '失恋'){ // 1 1
        process.nextTick(()=>{
            girl.emit(type);
        })
    }
})
// {'失恋':[fn,fn]}
let fn1 = function(){ // 默认这个方法在调用的时候
    console.log('监听到了 执行')
}
girl.once('失恋',fn1); // this.on('失恋',one); one.fn1
girl.off('失恋',fn1);  // one.fn1 != fn1
girl.once('失恋',function(){ // 默认这个方法在调用的时候
    console.log('监听到了 执行')
})

girl.emit('失恋');

// let listener1 = (w) => {
//     console.log('哭'+w)
// };
// let listener2 = (w) => {
//     console.log('逛街'+w)
// };
// girl.on("女生失恋", listener1);
// girl.on("女生失恋", listener2);
// // on emit => new Vue() $on $emit $once $on('change',function())
// girl.emit('女生失恋','我');

// 事件绑定 核心方法
// on emit once newListener off
// 作业


// fs 流 http
// koa
~~~

