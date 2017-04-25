## flexbox简介

　　CSS3引入了一种新的布局模式——Flexbox布局，即伸缩布局盒模型，用来提供一个更加有效的方式制定，调整和分布一个容器里的项目布局，即使它们的大小是未知或者动态的。主要思想是让容器有能力让其子项目能够改变其宽度，高度，以最佳方式填充可用空间（主要是为了适应所有类型的显示设备和屏幕大小）。Flex容器会使子项目扩展来填满可用空间，或缩小它们以防止溢出容器。
&emsp;&emsp;Flexbox布局的语法规范经过几年发生了很大的变化，主要经历了以下阶段:
* 2009年07月工作草案（display:box）;
* 2011年03月工作草案（display:flexbox）;
* 2011年11月工作草案（display:flexbox）;
* 2012年03月工作草案（display:flexbox）;
* 2012年06月工作草案（display:flex）;
* 2012年09月工作草案（display:flex）;

&emsp;&emsp;有关于浏览器支持情况可参考[caniuse.com](http://caniuse.com/)。

### 1.伸缩容器display
&emsp;&emsp;要开始使用Flexbox，必须先让父元素变成一个Flex容器。显式声明了Flex容器之后，一个Flexbox格式化上下文（Flexbox formatting context）就立即启动了。语法如下：
&emsp;&emsp;*display: flex | inline-flex*

 - flex: 设置为块伸缩容器。
 - inline-box: 设置为内联伸缩容器。

```css?linenums
.container{
	display: flex;
}
.container{
	display: inline-flex;
}
```
[demo](http://htmlpreview.github.io/?https://github.com/Vincken/flexbox/blob/master/flex%20demo/1.html)
### 1.伸缩流方向flex-direction
&emsp;&emsp;flex-direction属性控制Flex项目沿着主轴（Main Axis）的排列方向。简单点来说，就是flex-direction属性让你决定Flex项目如何排列。它可以是行（水平）、列（垂直）或者行和列的反向。从技术上讲，水平和垂直在Flex世界中不是什么方向（概念）。它们常常被称为主轴（Main-Axis）和侧轴（Cross-Axis）。默认设置如下所示。
![](https://github.com/Vincken/flexbox/raw/master/image/flex-direction.jpg)

&emsp;&emsp;*flex-direction: row | row-reverse | column | column-reverse*

 - flex: 设置为块伸缩容器。
 - inline-box: 设置为内联伸缩容器。

```css?linenums
.container{
	display: flex;
}
.container{
	display: inline-flex;
}
```
[demo](http://htmlpreview.github.io/?https://github.com/Vincken/flexbox/blob/master/flex%20demo/1.html)