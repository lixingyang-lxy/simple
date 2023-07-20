---
title: TS-learn
date: 2021-10-21 21:56:01
tags: TS-learn-语法进阶
---

## 第一章

> 配置文件 tsconfig.json

## 第二章

>  联合类型和类型保护

~~~typescript
namespace typeUnion {
    interface Bird {
        fly: boolean;
        sing: () => {};
    }
    interface Dog {
        fly: boolean;
        bark: () => {};
    }
    function trainAnimal(animal: Bird | Dog) {
        if (animal.fly) {
            (animal as Bird).sing()
            //这里使用as断言，用自己的逻辑来梳理类型
        }
        (animal as Dog).bark()
    }

    //in语法
    function trainAnimal2(animal: Bird | Dog) {
        if ('sing' in animal) {//这里使用in检索
            animal.sing()

        } else {//这里自动检测成除了Bird的情况
            animal.bark()
        }
    }

    //typeof语法
    function add(first: string | number, second: string | number) {
        if (typeof first === "number" && typeof second === "number")
            return first + second
        else {
            return first + '' + second
        }
    }
    console.log(add(1,'23'))

    //用instanceof来做类型保护，
    //需要用class而不是interface
    class NumberObj {
        constructor(public count: number) {}
    }
    function add2(first: object | NumberObj, second: object | NumberObj) {

        if (first instanceof NumberObj && second instanceof NumberObj) {
            return first.count + second.count
        }
        return 0
    }
    let f:NumberObj={count:1}
    let s:NumberObj=new NumberObj(2)
    console.log(add2(f,s))//这样f不行，0
    console.log(add2(new NumberObj(1),s))
    //这样可以，3,instanceof基于obj的原型链
    }
}
~~~

## 第三章

> Enum枚举类型   

~~~typescript
namespace Enum {
    const Status = {
        OFF: 0,
        ON: 1,
        ERR: 2,
    }
    //上面是js通常用法，可以用enum枚举代替
    //枚举通常从0开始赋值，但是也可以自定义数字，
    //比如OFF=1，就会1，2，3这样枚举
    //也可以ON=2，会变成0，2，3
    enum StatusEnum {
        OFF, 
        ON, 
        ERR
    }
    function getResult(status: number) {
        if (status === StatusEnum.OFF) {
            return 'off'
        } else if (status === StatusEnum.ON) {
            return 'on'
        }
        return 'err'
    }
    console.log(getResult(2), getResult(Status.ON), getResult(StatusEnum.OFF))
    console.log(StatusEnum)//{ '0': 'OFF', '1': 'ON', '2': 'ERR', OFF: 0, ON: 1, ERR: 2 }
}
~~~

