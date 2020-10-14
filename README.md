# JS_next
总结ES6及以后版本的JS新功能

- [JS_next](#js_next)
  - [一. 简介](#一-简介)
    - [1. 引入流程](#1-引入流程)
  - [二. ES6（2015）](#二-es62015)
    - [1. 对比``var``/``let``/``const``](#1-对比varletconst)
    - [2. 类``class``](#2-类class)
    - [3. 箭头函数](#3-箭头函数)
    - [4. 函数参数默认值](#4-函数参数默认值)
    - [5. 模板字符串](#5-模板字符串)
    - [6. 解构赋值](#6-解构赋值)
    - [7. 模块化（Module）](#7-模块化module)
    - [8. 扩展操作符](#8-扩展操作符)
    - [9. 对象属性简写](#9-对象属性简写)
    - [10. Promise](#10-promise)
    - [11. for…of](#11-forof)
    - [12. Symbol](#12-symbol)
    - [13. 迭代器（Iterator）/ 生成器（Generator）](#13-迭代器iterator-生成器generator)
    - [14. ``Set````/WeakSet``/``Map``/``WeakMap``](#14-setweaksetmapweakmap)
    - [15. Proxy/Reflect](#15-proxyreflect)
    - [16. Regex对象的扩展](#16-regex对象的扩展)
    - [17. Math对象的扩展](#17-math对象的扩展)
    - [18. Array对象的扩展](#18-array对象的扩展)
  - [三. ES7（2016）](#三-es72016)
    - [1. ``Array.prototype.includes``](#1-arrayprototypeincludes)
    - [2. 幂运算符**](#2-幂运算符)
  - [四. ES8（2017）](#四-es82017)
    - [1. ``async/await``](#1-asyncawait)
    - [2. 幂运算符**](#2-幂运算符-1)
    - [3. ``Object.values`` ``Object.entries``](#3-objectvalues-objectentries)
    - [4 ``Object.getOwnPropertyDescriptors``获取对象自身描述符的集合对象](#4-objectgetownpropertydescriptors获取对象自身描述符的集合对象)
    - [5. ``padStart`` ``padEnd``](#5-padstart-padend)
    - [6. 尾逗号](#6-尾逗号)
  - [四. ES9（2018）](#四-es92018)
    - [1. ``for await…of``异步迭代器](#1-for-awaitof异步迭代器)
    - [2. 后行断言](#2-后行断言)
    - [3. 正则表达式命名捕获组](#3-正则表达式命名捕获组)
    - [4. 对象扩展操作符](#4-对象扩展操作符)
    - [4. ``Promise.prototype.finally``](#4-promiseprototypefinally)
  - [五. ES10（2019）](#五-es102019)
    - [1. ``Array.prototype.flat``  ``Array.prototype.flatMap``](#1-arrayprototypeflat-arrayprototypeflatmap)
    - [2. ``String.prototype.trimStart`` ``String.prototype.trimLeft `` ``String.prototype.trimEnd`` ``String.prototype.trimRight``](#2-stringprototypetrimstart-stringprototypetrimleft-stringprototypetrimend-stringprototypetrimright)
    - [3. ``Object.fromEntries``](#3-objectfromentries)
    - [4. try-catch 可以不带异常参数](#4-try-catch-可以不带异常参数)
    - [5. import()动态导入返回promise](#5-import动态导入返回promise)
    - [6. ``Symbol.Description``](#6-symboldescription)
    - [7. ``BigInt``](#7-bigint)
    - [8. globalThis](#8-globalthis)
  - [六. ES11（2020）](#六-es112020)
    - [1 ``matchAll``](#1-matchall)
    - [2 动态``import``](#2-动态import)
    - [3 ``export * as ns from 'module'``](#3-export--as-ns-from-module)
    - [4 ``Promise.allSettled``](#4-promiseallsettled)
    - [5 ``BigInt``](#5-bigint)
    - [6 ``GlobalThis``](#6-globalthis)
    - [7 Nullish coalescing Operator ``??``](#7-nullish-coalescing-operator-)
    - [8 Optional Chaining ``?.``](#8-optional-chaining-)

## 一. 简介
### 1. 引入流程
status|特点
-|-
0|提交想法
1|形成提案
2|大概率通过1.0版本
3|完善细节
4|准备添加到标准中

## 二. ES6（2015）
### 1. 对比``var``/``let``/``const``
> - **暂时性死区** 根据规范，``let``/``const``在上下文创建的时候，变量已经创建，但是还没有跟词法绑定，直到该变量被声明才可以被访问，这就是所谓的暂时性死区，按照这个结论，``let``/``const``也是有变量提升的

```js
// The variables are created when their containing Lexical Environment is instantiated but may not be accessed instant way until the variable’s LexicalBinding is evaluated.
```

> - var 存在提升，我们能在声明之前使用。 let 、 const 因为暂时性死区的原因，不能在声明前使用
> - var 在全局作用域下声明变量会导致变量挂载在 window 上，其他两者不会

要点|``var``|``let``|``const``
-|-|-|-
变量提升|✔|❌|❌
暂时性死区|❌|✔|✔
### 2. 类``class``
> - 函数+原型构建 -> ``class``
### 3. 箭头函数
> - 适用于匿名函数，没有``this``，``arguments``，``super``或 ``new.target`` 
### 4. 函数参数默认值
### 5. 模板字符串
```js
    const keyValueMap = {
        a: 1,
        b: 2,
        c: 3
    }
    function stringTemplate(str) {
        return str.replace(/\$\{.+?\}/g, keys => keyValueMap[keys.slice(2, -1)]);
    }
```
### 6. 解构赋值
### 7. 模块化（Module）
### 8. 扩展操作符
> - 扩展操作符只能用于可迭代对象
### 9. 对象属性简写
### 10. Promise
### 11. for…of
### 12. Symbol
> - 静态属性和静态方法
> - 不支持语法``new Symbol()``。
### 13. 迭代器（Iterator）/ 生成器（Generator）
> - ``function*`` 和 ``yield``
> - 为了实现可迭代，一个对象必须实现 @@iterator 方法，这意味着这个对象（或其原型链中的任意一个对象）必须具有一个带 Symbol.iterator 键（key）的属性。
```js
        a = {
            [Symbol.iterator]: function iterator() {
                    const arr = [1, 2, 3];
                    let i = 0;    
                    return {
                        next: () => {
                            const result = {value: arr[i], done: i === arr.length};
                            i++;
                            return result;
                        }
                    };
                }
        }
        for(let i of a) console.log(i);
        1
        2
        3
        undefined
}
```
### 14. ``Set````/WeakSet``/``Map``/``WeakMap``
> -  ``Set`` vs ``WeakSet`` ``WeakSet``  对象中存储的对象值都是被弱引用的, 弱引用是指当对象被回收时在``WeakSet``中不可被枚举, 不能存放值，而Set都可以
> -  ``Map`` vs ``WeakMap`` ``WeakMap`` 对象的key中只能存放正在被引用的对象引用, 不能存放值, 而 ``Map`` 对象都可以。

### 15. Proxy/Reflect
```js
        const observe = (data, callback) => {
            return new Proxy(data, {
                    get(target, key) {
                        return Reflect.get(target, key)
                    },
                    set(target, key, value, proxy) {
                        cb(key, value);
                        target[key] = value;
                            return Reflect.set(target, key, value, proxy)
                    }
            })
        }
```
### 16. Regex对象的扩展
> - 以前： i(是否执行大小写不敏感匹配，设置了就不区分大小写)、m(多行匹配)、g(全局匹配)。
> - u 修饰符：``Unicode``模式，用来正确处理大于\uFFFF的``Unicode``字符。
> - y 修饰符：“粘连”``sticky``。用来正确处理匹配粘连的字符串。
> - s 修饰符： ``dotAll`` 模式，即点（dot）代表一切字符。
### 17. Math对象的扩展
> - 比较多
### 18. Array对象的扩展
> - ``Array.prototype.from`` 转换具有Iterator接口的数据结构为真正数组，返回新数组
> - ``Array.prototype.of`` 转换一组值为真正数组，返回新数组。
> - ``Array.prototype.copyWithin`` 在当前数组内部，将指定位置的成员复制到其他位置（会覆盖原有成员），然后返回当前数组
>> - ``target``（必需）：从该位置开始替换数据。如果为负值，表示倒数。
>> - ``start``（可选）：从该位置开始读取数据，默认为 0。如果为负值，表示从末尾开始计算。
>> - ``end``（可选）：到该位置前停止读取数据，默认等于数组长度。如果为负值，表示从末尾开始计算。
```js
        [0,1,2,3,4,5,6,7,8].copyWithin(1, 5, 7); // [0, 5, 6, 3, 4, 5, 6, 7, 8]
```
> - ``Array.prototype.find``和``Array.prototype.findIndex``
> - ``Array.prototype.keys`` ``Array.prototype.values`` ``Array.prototype.entries``
> - 数组空位：ES6明确将数组空位转为``undefined``或者``empty``

## 三. ES7（2016）
### 1. ``Array.prototype.includes``
### 2. 幂运算符**

## 四. ES8（2017）
### 1. ``async/await``
### 2. 幂运算符**
### 3. ``Object.values`` ``Object.entries``
### 4 ``Object.getOwnPropertyDescriptors``获取对象自身描述符的集合对象
```js
        const b = Object.getOwnPropertyDescriptors({a: 1});
        b.a // {value: 1, writable: true, enumerable: true, configurable: true}
```

### 5. ``padStart`` ``padEnd``
### 6. 尾逗号
> - 以前只支持对象
> - 现在也支持函数的参数和解构，但不支持剩余参数和空参数之后添加尾逗号

## 四. ES9（2018）
### 1. ``for await…of``异步迭代器
```js
        async function* asyncGenerator() {
        var i = 0;
        while (i < 3) {
            yield i++;
        }
        }

        (async function() {
        for await (num of asyncGenerator()) {
            console.log(num);
        }
        })();
        // 0
        // 1
        // 2
```

### 2. 后行断言
> - 以前： 先行断言 x只有在y前面才匹配，必须写成``/x(?=y)/``，否定形式``/x(?!y)/``
> - 后行断言: x只有在y后面才匹配，必须写成``/(?<=y)x/``
### 3. 正则表达式命名捕获组
### 4. 对象扩展操作符
> - ES6的扩展操作符只支持数组，ES9支持对象了
> - ``Object.assign``会触发``setters``，而展开语法则不会。所以不能替换也不能模拟``Object.assign``
### 4. ``Promise.prototype.finally``
```js
        fetch(url)
        .then((res) => {
            console.log(res)
        })
        .catch((error) => { 
            console.log(error)
        })
        .finally(() => { 
            console.log('结束')
        })
```
## 五. ES10（2019）
### 1. ``Array.prototype.flat``  ``Array.prototype.flatMap``
> - ``Array.prototype.flat`` 默认打平一层数组，如果要多层就传入参数, 如果原数组有空位，flat方法会跳过空位
> - ``Array.prototype.flatMap`` 只能展开一层数组进行遍历
### 2. ``String.prototype.trimStart`` ``String.prototype.trimLeft `` ``String.prototype.trimEnd`` ``String.prototype.trimRight``
### 3. ``Object.fromEntries``
### 4. try-catch 可以不带异常参数
### 5. import()动态导入返回promise
### 6. ``Symbol.Description``
> - 返回只读的描述字符串
### 7. ``BigInt`` 
> - 任意精度整数
> - 第7种原始类型
```js
const limit = Number.MAX_SAFE_INTEGER; // 9007199254740991
limit + 1; // 9007199254740992
limit + 2; // 9007199254740992 // exceed

const larger = 9007199254740991n; // 9007199254740991n
const integer = BigInt(9007199254740991); // initialize with number 9007199254740991n
const same = BigInt("9007199254740991"); // initialize with "string" 9007199254740991n
```
### 8. globalThis
> - 兼容所有平台的全局作用域
## 六. ES11（2020）
### 1 ``matchAll``
### 2 动态``import``
### 3 ``export * as ns from 'module'``
### 4 ``Promise.allSettled``
### 5 ``BigInt``
### 6 ``GlobalThis``
### 7 Nullish coalescing Operator ``??``
### 8 Optional Chaining ``?.``