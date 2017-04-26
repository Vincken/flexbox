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

&emsp;&emsp;`display: flex | inline-flex`

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
### 2.伸缩流方向flex-direction
&emsp;&emsp;flex-direction属性控制Flex项目沿着主轴（Main Axis）的排列方向。简单点来说，就是主轴的方向。它可以是行（水平）、列（垂直）或者行和列的反向。从技术上讲，水平和垂直在Flex世界中不是什么方向（概念）。它们常常被称为主轴（Main-Axis）和交叉轴（Cross-Axis）。默认设置如下所示。
![](https://github.com/Vincken/flexbox/raw/master/image/flex-direction.jpg)

&emsp;&emsp;`flex-direction: row | row-reverse | column | column-reverse`

 - row（默认值）：主轴为水平方向，项目从左到右排列(默认情况)。
 - row-reverse：主轴为水平方向，项目从右到左排列(默认情况)。
 - column：主轴为垂直方向，项目从上到下排列(默认情况)。
 - column-reverse：主轴为垂直方向，项目从下到上排列(默认情况)。

```css?linenums
.container{
	display: flex;
	flex-direction: row;
}
```
[demo](http://htmlpreview.github.io/?https://github.com/Vincken/flexbox/blob/master/flex%20demo/2.html)
### 3.伸缩换行flex-wrap
&emsp;&emsp;flex-wrap主要用来定义伸缩容器里是单行还是多行显示，交叉轴的方向决定了新行堆放的方向。

&emsp;&emsp;`flex-wrap: nowrap | wrap | wrap-reverse`

 - nowrap（默认值）: 不换行。
 - wrap: 换行，第一行在上方。
 - wrap-reverse: 换行，第一行在下方。

```css?linenums
.container{
	display: flex;
	flex-wrap: no-wrap;
}
```
[demo](http://htmlpreview.github.io/?https://github.com/Vincken/flexbox/blob/master/flex%20demo/3.html)
### 4.伸缩方向和换行flex-flow
&emsp;&emsp;flex-flow是flex-direction和flex-wrap两个属性的速记属性。
&emsp;&emsp;`flex-flow: <'flex-direction'> || <'flex-wrap'>`
### 5.主轴对齐justify-content
&emsp;&emsp;justify-content属性主要定义了Flex项目在Main-Axis上的对齐方式。

&emsp;&emsp;`justify-content: flex-start | flex-end | center | space-between | space-around`

 - flex-start（默认值）: 让伸缩项目向Main-Axis开始边缘对齐。
 - flex-end: 让伸缩项目向Main-Axis结束边缘对齐。
 - center: 让伸缩项目向Main-Axis中间位置对齐。
 - space-between: 项目之间的间距相等（两端对齐）。
![](https://github.com/Vincken/flexbox/raw/master/image/space-between.jpeg)
 - space-around: 每个项目两侧的间隔相等。
![](https://github.com/Vincken/flexbox/raw/master/image/space-around.jpeg)
```css?linenums
.container{
	display: flex;
	justify-content: flex-start;
}
```
[demo](http://htmlpreview.github.io/?https://github.com/Vincken/flexbox/blob/master/flex%20demo/4.html)
### 6.伸缩换行align-items
&emsp;&emsp;align-items定义了Flex项目在Cross-Axis上的对齐方式。

&emsp;&emsp;`align-items: stretch | flex-start | flex-end | center | baseline`

 - stretch（默认值）: 伸缩项目填充整个伸缩容器，会在控制大小的属性的限制下尽可能接近所在容器的尺寸。
 - flex-start : 让伸缩项目向Cross-Axis开始边缘对齐。
 - flex-end: 让伸缩项目向Cross-Axis结束边缘对齐。
 - center: 让伸缩项目向Cross-Axis中间位置对齐。
 - baseline: 让伸缩项目在Cross-Axis上沿着他们自己的基线对齐。

```css?linenums
.container{
	display: flex;
	align-items: stretch;
}
```
[demo](http://htmlpreview.github.io/?https://github.com/Vincken/flexbox/blob/master/flex%20demo/5.html)
### 7.显示顺序order
&emsp;&emsp;order定义了定义项目的排列顺序。数值越小，排列越靠前，默认为0。

&emsp;&emsp;`order: <number>`

```css?linenums
.item{
	order: 3;
}
```
[demo](http://htmlpreview.github.io/?https://github.com/Vincken/flexbox/blob/master/flex%20demo/6.html)
### 8.交叉轴对齐align-self
&emsp;&emsp;align-self用来设置单独伸缩项目在交叉轴的对齐方式，可覆盖伸缩容器的align-items属性，取值和align-items一样。

&emsp;&emsp;`align-self: stretch | flex-start | flex-end | center | baseline`

```css?linenums
.item{
	align-self: center;
}
```
[demo](http://htmlpreview.github.io/?https://github.com/Vincken/flexbox/blob/master/flex%20demo/7.html)
### 9.放大比例flex-grow
&emsp;&emsp;flex-grow定义项目的放大比例，默认为0，表示有多余空间时，项目也不放大。

&emsp;&emsp;`flex-gorw: <number> `

```css?linenums
.item{
	flex-grow: 1;
}
```
[demo](http://htmlpreview.github.io/?https://github.com/Vincken/flexbox/blob/master/flex%20demo/8.html)
### 10.缩小比例flex-shrink
&emsp;&emsp;flex-shrink属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。

&emsp;&emsp;`flex-shrink: <number> `

```css?linenums
.item{
	flex-shrink: 1;
}
```
[demo](http://htmlpreview.github.io/?https://github.com/Vincken/flexbox/blob/master/flex%20demo/9.html)
### 11.伸缩基准值flex-basis
&emsp;&emsp;flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。

&emsp;&emsp;`flex-basis: <length> | auto `

```css?linenums
.item{
	flex-basis: 200px;
}
```
[demo](http://htmlpreview.github.io/?https://github.com/Vincken/flexbox/blob/master/flex%20demo/10.html)
### 12.伸缩性flex
&emsp;&emsp;flex是flex-grow、flex-shrink和flex-basis三个属性的简写。

&emsp;&emsp;`flex: none | [ <'flex-grow'> <'flex-shrink'> <'flex-basis'> ] `

```css?linenums
.item{
	flex: 0 1 auto;
}
```
