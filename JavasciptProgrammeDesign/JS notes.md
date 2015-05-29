
#Javascript程序设计目录

+ [JS介绍](#JS介绍)
  + [JS介绍~](#JS介绍~) 
     + [前端开发三要素](#前端开发三要素)
     + [Javascript](#javascript)
     + [浏览器中的JS](#浏览器中的js)
     + [JS引入](#js引入)
##JS介绍

###JS介绍~

#### 前端开发三要素

* HTML-内容
* CSS-样式
* Javascript-控制浏览器和网页的行为
  * 改变HTML元素、结构
  * CSS样式
  * 对时间做出相应
  * 实现和服务器端交互

#### Javascript

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

ECMA-262第5版定义的严格模式下保留字和ECMA-262第3版保留字[参见](http://www.68idc.cn/help/makewebs/javascript/20141107127194.html)
