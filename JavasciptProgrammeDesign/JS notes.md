
#JavaScript程序设计笔记

+ [JS介绍](#js介绍)
  + [JS介绍~](#js介绍~) 
     + [前端开发三要素](#前端开发三要素)
     + [Javascript](#javascript)
     + [浏览器中的JS](#浏览器中的js)
     + [JS引入](#js引入)
+ [调试器](#调试器)
  + [调试器~](#调试器~)
     + [JS调试](#js调试) 
+ [基本语法](#基本语法)
  + [基本语法~](#基本语法~)
      + [词法重点](#词法重点)
     
## JS介绍

###JS介绍~

#### 前端开发三要素

* HTML-内容
* CSS-样式
* JavaScript-控制浏览器和网页的行为
  * 改变HTML元素、结构
  * CSS样式
  * 对时间做出相应
  * 实现和服务器端交互

#### JavaScript

* 解释型（脚本）语言

* 运行环境：一般以为是浏览器，但实际上是浏览器搭载的JS引擎。（eg.node.js的V8引擎）

* 发展历史
   * 解决表单验证:网景推出livescript
  * 为了推广：与Sun合作，更名javascript
  * 制定语言标准：ECMAScript 1.0
  * 使用JS动态修改HTML内容：网景和分别微软推出DHTML
  * W3C:DOM
  * ECMAScript 3.0
  * Ajax
  * ECMAScript 5.1
  * ECMAScript 6：2015年6月发布

![history]()

#### 浏览器中的JS
 
* ECAMScript
  * JS核心语言标准

* DOM：W3C标准
  * W3C规定的标准
  * 调用、操作文档中的API

* BOM
  * 调用、操作浏览器中的API
  * 没有明确规范定义，但它实现的API，在W3C中有大量定义

#### JS引入
* 内嵌代码
内嵌入HTML文档中靠近<code>&lt;body></code>标签**结束处**。具体原因参见讨论：

> [JavaScript 的性能优化：加载和执行](https://help.github.com/articles/github-flavored-markdown/)
> 
> [浏览器的渲染原理简介](http://coolshell.cn/articles/9666.html)

内嵌方法示例：
```html
<body>
	<script type="text/javascript">
		document.write("Hello,world")
	</script>
</body>
```

* 外部引入

外引方法示例示例

```html
<body>
	<script type="text/javascript" src="demo.js">
	</script>
</body>
```
## 调试器

### 调试器~

#### JS调试

* Firefox

  * 一般使用**firebug**进行调试。

  * **F12**调用调试工具。

* IE9以上也提供了开发者工具

  * 需要点击**调试开始**才能进行代码调试。

* Chrome

  * **右键**审查元素或**F12**调出开发者工具

  * Chrome开发者工具介绍：
  >[云课堂讨论区](http://mooc.study.163.com/learn/NEU-1000054003#/learn/content?type=detail&id=1000146074&cid=1000133142)
  >
  >[文章：神器——Chrome开发者工具(一)](http://segmentfault.com/a/1190000000683599)
  >
  >[课程：Explore and Master
Chrome DevTools](http://discover-devtools.codeschool.com/)
  >
  >[短视频：chrome-devtools](http://haoduoshipin.com/v/40?autoplay=true)

## 基本语法

### 基本语法~

#### 词法重点

* 变量标识符

  * 命名要求
  
      * 字母、下划线(_)或美元符号(&)开头
      
      * 由字母、下划线(_)、美元符号(&)或数字组成
   * 范例
   ```javascript
   // 正确
   var abc
   var _abc
   var $abc
   var _abc1$
   function $$abc_ () {
   
   }
   
    // 错误
  var 1abc
  var *abc
  var abc&
  function #abc () {
}
   ```

* 关键字和保留字

    |关键字||||
    |---|---|---|---|
    |break|do|instanceof|typeof|
    |case|else|new|var|
    |catch|finally|return|void|
    |continue|for|switch|while|
    |debugger*|function|this|with|
    |default|if|throw|delete|
    |in|try|||

  *以上为ECMA-262定义的关键词， \*号词为ECMAScript5新增*
  
     |保留字||||
     |---|---|---|---|
     |class|enum|extend|super|
     |const|export|inport||
 
    *以上为ECMA-262第5版定义的**非严格模式**下保留字*

    ECMA-262第5版定义的严格模式下保留字和ECMA-262第3版保留字参见[Javascript中的关键字和保留字整理](http://www.68idc.cn/help/makewebs/javascript/20141107127194.html)

    定义变量时，如果变量命名与关键字或保留字**冲突**，则报错。

* 大小写敏感
  * 范例
    ```javascript
    var arr = [1, 2, 3] 

    var Arr = function () {
        For (var i = 0; i < A; i++) {
            console.log(A[i])
        }
    }
    // Arr与arr大小写不同，会被JavaScript识别为不同变量

    // for循环关键字应为小写，所以大写时JavaScript将无法识别。
    ```

* 严格模式
EMACScript第5版引入

  * 增益
     * 消除js语法的不合理、不严谨与不安全问题，减少怪异行为并保证代码运行安全
     
     * 提高编译器效率，增加运行速度
  * 使用
     * 全局使用严格模式：在script脚本第一行加入<code>“use strict";</code>
    ```html 
    <script type="text/javascript">
    "use strict";
    (function () {
	    console.log("Hello, world!")
	 })()
	 </script>
    ```
     * 函数内使用严格模式:在函数内加入<code>“use strict";</code>
       ```html 
       <script type="text/javascript">
       (function () {
       "use strict";
	   console.log("Hello, world!")
	   })()
	   </script>
       ```
  * 严格模式和标准模式对比
     * 隐式声明或定义变量（函数内定义一个未声明变量）
     
            |标准模式|严格模式|
            |---|---|
            |在全局定义一个新变量<br>windows.var == value|ReferenceError：var is not defined|

     * 对象重名的属性

            |标准模式|严格模式|
            |---|---|
            |允许重名|SyntaxError| 
     范例
     ```javascript
     var abc = {a:1, b:2, a:3}; 
     
     // 标准模式: a == 3
     
     // 严格模式: SyntaxError
     ```
   
     * arguments.callee(关于callee的[介绍](http://blog.sina.com.cn/s/blog_616acf520100nosr.html))
     
            |标准模式|严格模式|
            |---|---|
            |允许使用匿名函数调用自身|TypeError| 
    范例
     ```javascript
     var count = 0; 
     (function () {
         if (count > 10) {
             return;
         };
         count++;
         arguments.callee;
         
     // 允许使用
     
     // 严格模式: TypeError
     ```

     * with

            |标准模式|严格模式|
            |---|---|
            |允许使用with语句方便书写|SyntaxError| 
     范例
     ```javascript
     var x, y; 
     var count = 0; 
     (function () {
         with(Math) {
             x = cos(3 * PI) + sin(LN10)
             y = tan(14 * E)
         
     // 允许使用
     
     // 严格模式: SyntaxError
     ```

     * 更多差异，参阅[Javascript 严格模式详解](http://www.ruanyifeng.com/blog/2013/01/javascript_strict_mode.html)或[ES5严格模式（Strict mode）](http://www.cnblogs.com/snandy/p/3428171.html)
 