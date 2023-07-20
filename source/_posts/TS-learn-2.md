---
title: TS-learn-2
date: 2021-10-21 22:46:55
tags: TS-learn-2
---

## 第四章

> 函数泛型和类泛型

~~~typescript
// 函数泛型
namespace functionGeneric {
    // function join(first:string|number,second:string|number){
    //     return `${first}${second}`
    // }
    //如果我想保证两个参数同类型但不一定是什么类型，就要用泛型
    function join<T>(first: T, second: T) {
        return `${first}${second}`
    }
    //join<number>(1,'1')//报错
    //join<string>(1,1)//报错
    console.log(join(1, 1), join<string>('1', '1'))//这样是可以的，不写泛型也会自动推断

    function map<M>(params:M[],_:Array<M>){//指M数组,M[]和Array<M>差不多
        return params.concat(_)
    }
    console.log(map<string>(['123'],['0']))
}
~~~

~~~typescript
// 类泛型
namespace classGeneric {
    class DataManager<T>{
        constructor(private data: T[]) { }
        getItem(index: number) {
            return this.data[index]
        }
    }
    const data = new DataManager(['1', '2', '3'])//类自动进行了推断
    console.log(data.getItem(1))
    const numbers = new DataManager<number>([1, 2, 3])
    console.log(numbers)

    //让泛型继承接口，会限制格式
    interface Obj {
        name: string
    }
    class DataManager1<T extends Obj>{
        constructor(private data: T[]) { }
        getItem(index: number) {
            return this.data[index].name
        }
    }
    const data1 = new DataManager1<Obj>([{ name: 'dell' }])
    console.log(data.getItem(0))

    class DataManager2<T extends number | string>{//让T只能是某些类型
        constructor(private data: T[]) { }
        getItem(index: number): T {
            return this.data[index]
        }
    }
    interface Test {
        name: string
    }
    const data2 = new DataManager2<string>([''])

    //泛型和函数
    const fun: <T>(a: T) => string
        = <T>(a: T) => '123'
    console.log(fun<number>(0))
}
~~~

## 第五章

> 命名空间

~~~typescript
// 命名空间上
namespace nameSpaces{
    interface Person {
        name: string;
        age: number;
        gender?: string;
    }
    class Teacher {
        constructor(private info: Person) { }
        getInfo<T extends keyof Person>(key: T) {
            //type T='name'|'age'|'gender'
            //keyof 通过遍历Person上的属性保证了T类型属于Person的属性的类型
            return this.info[key]
        }
    }
    const teacher = new Teacher({
        name: 'teacher',
        age: 30,
        gender: 'male'
    })
    const name = teacher.getInfo('name')
    const age = teacher.getInfo('age')
    const gender = teacher.getInfo('gender')
    console.log(name,age,gender)
}
~~~

~~~typescript
// 命名空间下
namespace Demo {
    class Header {
        constructor() {
            const elem = document.createElement('div')
            elem.innerText = 'Header'
            elem.setAttribute('style', 'background-color:red')
            document.body.appendChild(elem)
        }
    }
    class Content {
        constructor() {
            const elem = document.createElement('div')
            elem.innerText = 'Content'
            elem.setAttribute('style', 'background-color:red')
            document.body.appendChild(elem)
        }
    }
    class Footer {
        constructor() {
            const elem = document.createElement('div')
            elem.innerText = 'Footer'
            elem.setAttribute('style', 'background-color:red')
            document.body.appendChild(elem)
        }
    }
    export class Page {//暴露加export
        constructor() {
            new Header()
            new Content()
            new Footer()
        }
    }
    export const a = 1
    export const b = 2
}


~~~

~~~typescript
// 命名空间相互引用

// components.ts
namespace Components {
    export namespace SubComponents {
        export interface User {
            name: string
        }
    }
    export class Header {
        constructor() {
            const elem = document.createElement('div')
            elem.innerText = 'Header'
            elem.setAttribute('style', 'background-color:red')
            document.body.appendChild(elem)
        }
    }
    export class Content {
        constructor() {
            const elem = document.createElement('div')
            elem.innerText = 'Content'
            elem.setAttribute('style', 'background-color:red')
            document.body.appendChild(elem)
        }
    }
    export class Footer {
        constructor() {
            const elem = document.createElement('div')
            elem.innerText = 'Footer'
            elem.setAttribute('style', 'background-color:red')
            document.body.appendChild(elem)
        }
    }
}
    
// page.ts
///<reference path='./components.ts'/>
// 上边这句话代表命名空间的引入路径
namespace Demo {
    export class Page {//暴露加export
        constructor() {
            new Components.Header()
            new Components.Content()
            new Components.Footer()
            let n: Components.SubComponents.User = {
                name: 'name'
            }
            console.log(n)
        }
    }
    export const a = 1
}


~~~

