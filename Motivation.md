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

MODULE SYSTEM STYLES(模块系统风格)
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
## `<script>` -tag style

This is how you would handle a modularized code base if you didn’t use a module system.

```html
<script src="module1.js"></script>
<script src="module2.js"></script>
<script src="libraryA.js"></script>
<script src="module3.js"></script>
```

