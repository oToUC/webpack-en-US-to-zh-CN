MOTIVATION(动机)
--
Today’s websites are evolving into web apps:
+ More and more JavaScript is being used.
+ Modern browsers are offering a wider range of interfaces.
+ Fewer full page reloads → even more code in a page.

As a result there is a lot of code on the client side!

A big code base needs to be organized. Module systems offer the option to split your code base into modules.

--
今天的网站已经逐渐演化成 web apps：
+ 越来越多的javascript正被使用
+ 现代浏览器都提供广泛的接口。
+ 更少的全页面刷新——甚至更多代码在一个页面中

结果是有大量的代码在客户端

一个大的代码库需要被组织。模块系统提供选择去拆分你的代码库成多个模块。

###MODULE SYSTEM STYLES(模块系统风格)
--
There are multiple standards for how to define dependencies and export values:
+ `<script>`-tag style (without a module system)
+ CommonJS
+ AMD and some dialects of it
+ ES6 modules
+ and more…

--
有许多的标准给如何定义依赖和导出值：
+ `<script>`-标签风格(在模块系统之外)
+ CommonJS
+ AMD 和它的一些分支
+ ES6 modules
+ 更多……

--
### `<script>` -tag style

This is how you would handle a modularized code base if you didn’t use a module system.

```html
<script src="module1.js"></script>
<script src="module2.js"></script>
<script src="libraryA.js"></script>
<script src="module3.js"></script>
```
Modules export an interface to the global object, i. e. the window object. Modules can access the interface of dependencies over the global object.

--
如果你之前没有用过模块系统，这个风格将是你如何处理一个模块化后的代码库。

各个模块导出一个接口给全局对象。既window对象。各个模块能通过全局对象访问依赖的接口

--
Common problems
* Conflicts in the global object.
* Order of loading is important.
* Developers have to resolve dependencies of modules/libraries.
* In big projects the list can get really long and difficult to manage.

常见问题
* 全局对象的冲突
* 加载顺序非常重要。
* 开发人员不得不解决模块和库的依赖关系
* 在大项目中这个列表会真正的变的很长并且难以管理

###CommonJs: synchronous require
--
This style uses a synchronous require method to load a dependency and return an exported interface. A module can specify exports by adding properties to the exports object or setting the value of module.exports.

--
###CommonJs: 同步require
--
这种风格使用同步require方法来加载依赖项，并返回一个导出的接口。模块可以通过将添加属性到exports对象或设置 module.exports 的值指定导出。


```javascript
require("module");
require("../file.js");
exports.doStuff = function() {};
module.exports = someValue;
```

It’s used server-side by node.js.

它通过node.js被用于服务端。

###Pros
+ Server-side modules can be reused.
+ There are already many modules written in this style (npm).
+ Very simple and easy to use.

###Cons
+ Blocking calls do not apply well on networks. Network requests are asynchronous.
+ No parallel require of multiple modules

###Implementations
+ node.js - server-side
+ browserify
+ modules-webmake - compile to one bundle
+ wreq - client-side


###优点
+ 服务端模块可重用
+ 这种风格已经有许多模块采用编写(npm)
+ 非常简单并且易用

###缺点
+ 阻塞调用在网络上不适用。网络请求应是异步的。
+ 多模块没有平行请求

###Implementations (实现)
* [node.js](http://nodejs.org/) - server-side
* [browserify](https://github.com/substack/node-browserify)
* [modules-webmake](https://github.com/medikoo/modules-webmake) - compile to one bundle
* [wreq](https://github.com/substack/wreq) - client-side

###AMD: asynchronous require
Asynchronous Module Definition

Other module systems (for the browser) had problems with the synchronous require (CommonJS) and introduced an asynchronous version (and a way to define modules and exporting values):










