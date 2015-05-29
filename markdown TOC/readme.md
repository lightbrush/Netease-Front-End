
# Markdown ToC(Table of Content)

##介绍
上网查怎么给markdown制作目录的时候，发现了一个非常棒侧边栏目录方案，作者Github[地址](https://github.com/i5ting/i5ting_ztree_toc)。

因为我本人比较新手，对**jQuery**完全没什么了解，对着作者的demo琢磨了半天，又参考了网上[另一篇文章](http://www.jianshu.com/p/34c92cbd0aaf/)精简版代码，才最终实现了作者的方案。接着我又导入了自己常用的Markdown编辑器[Stackedit](https://stackedit.io/)的css和js代码，最终做出了成品。现在我整理了一下实现这个方案需要的相关代码和实现步骤，传到Github上，以作记录。

![示例](http://ww4.sinaimg.cn/bmiddle/6a02f707gw1esl9zvzhocg20c806djtw.gif)

## 步骤

1. 下载js,css文件夹和template.html。

 + Template中的<code>&lt;article\>...&lt;article></code>标签内为你的正文放置区域。

2. 将你的MD文件转换为HTML文件，建议使用Stackedit (Export to disk-Using template)。将HTML的正文部分复制到Template中，保存。

3. 设置好Title，Favicon或其他标签，完成。

