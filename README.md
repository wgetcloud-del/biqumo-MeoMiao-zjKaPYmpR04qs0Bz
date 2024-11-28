
## 1、什么是弹性布局


Flex是Flexible Box的缩写，翻译成中文就是“弹性盒子”，用来为盒装模型提供最大的灵活性。任何一个容器都可以指定为Flex布局。


她是一种现代的CSS布局方式，通过使用display: flex属性来创建一个弹性容器，可以自动适配各种设备的不同宽度，而不必依赖于传统的块状布局和浮动定位，并在其中使用灵活的盒子模型来进行元素的排列和定位。


在浏览器支持完美的环境中，选择使用弹性盒子的原因是你希望把一系列项目沿着同一方向布局。因为在放置元素过程中，你想控制元素在那个方向的维度，或者控制它们彼此之间的间距。弹性盒子就是为此设计的。


## 2、弹性布局的特点


* 主轴与交叉轴：弹性容器具有主轴（main axis）和交叉轴（cross axis）。默认情况下，主轴是水平方向，交叉轴是垂直方向。
* 弹性容器：通过将父元素的display属性设置为flex或inline\-flex来创建弹性容器。
* 子元素的弹性项目：弹性容器中的每个子元素都成为弹性项目。子元素可以指定各自在主轴和交叉轴上的大小、顺序以及对齐方式等。
* 主轴对齐：弹性项目可以在主轴上按照一定比例分配空间，也可以使用justify\-content属性定义主轴的对齐方式。
* 交叉轴对齐：弹性项目可以在交叉轴上进行对齐，包括顶部对齐、底部对齐、居中对齐等，使用align\-items属性定义交叉轴对齐方式。
* 换行与自动调整：可控制弹性项目是否换行，并且具备自动调整元素大小的能力。
* 弹性布局简化了网页布局的开发过程，提供了更灵活、响应式的布局方式。它适用于各种屏幕尺寸和设备类型，并能够快速适应不同的布局需求。


![弹性布局](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129181-1556859190.png)


## 3、Flex容器


我们把一个容器的 display 属性值改为 flex 或者 inline\-flex 之后，该容器就变成了 Flex 容器，而容器中的直系子元素就会变为 flex 元素。如下代码所示，parent 元素就是 Flex 容器，son 元素就是 Flex 元素。


![Flex容器](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129444-762647077.png)



```
<style>
#parent {
    display: flex;
}
style>
<div id="parent">
    <div id="son">div>
div>

```

由于所有 CSS 属性都会有一个初始值，所以 flex 容器中的所有 flex 元素都会有下列行为：


* 元素排列为一行（`flex-direction` 属性的初始值是 `row`）。
* 元素从主轴的起始线开始。
* 元素不会在主维度方向拉伸，但是可以缩小。
* 元素被拉伸来填充交叉轴大小。
* [`flex-basis`](https://github.com) 属性为 `auto`。
* [`flex-wrap`](https://github.com) 属性为 `nowrap`。


## 4、Flex容器属性


![Flex容器属性](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129242-171256551.png)


### 4\.1、flex\-direction：决定主轴的方向（即项目的排列方向）



```
.box {
   flex-direction: row | row-reverse | column | column-reverse;
}

```

如果你选择了 row 或者 row\-reverse，那么主轴（Main Axis）就是横向的 X 轴，交叉轴（Cross Axis）就是竖向的 Y 轴，如下图所示。


![主轴是横向的X轴，交叉轴是竖向的Y轴](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129431-502938689.jpg)


如果你选择了 column 或者 column\-reverse，那么主轴（Main Axis）就变成是竖向的 Y 轴，交叉轴（Cross Axis）就是横向的 X 轴，如下图所示。


![主轴是竖向的Y轴，交叉轴是横向的X轴](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129417-8517755.jpg)


* row（默认值）：主轴为水平方向，起点在左端。
* row\-reverse：主轴为水平方向，起点在右端。
* column：主轴为垂直方向，c起点在上沿。
* column\-reverse：主轴为垂直方向，起点在下沿。


![flex-direction：决定主轴的方向（即项目的排列方向）](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129412-371124386.png)


### 4\.2、flex\-wrap：定义换行情况


* nowrap（默认）：不换行。
* wrap：换行，第一行在上方。
* wrap\-reverse：换行，第一行在下方。


![flex-wrap：定义换行情况](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129212-2019849866.webp)


默认元素排列在一条轴线上，如果一条轴线排不下，此时就可以用flex\-wrap属性处理。



```
.box{
   flex-wrap: nowrap | wrap | wrap-reverse;
}

```

* **nowrap（默认）：不换行**


![nowrap（默认）：不换行](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129437-1316020741.png)


* **wrap：换行，第一行在上方**
![wrap：换行，第一行在上方](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129456-1660046529.png)
* **wrap\-reverse：换行，第一行在下方**


![wrap-reverse：换行，第一行在下方](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129238-1491870516.png)


### 4\.3、justify\-content：定义项目在主轴上的对齐方式


justify\-content 属性用来使元素在主轴方向上对齐，它的初始值是 flex\-start，即元素从容器的起始线排列。justify\-content 属性有如下 5 个不同的值：


* flex\-start（默认值）：左对齐、从起始线开始排列，默认值。
* flex\-end：右对齐、从终止线开始排列。
* center： 居中、在中间排列。
* space\-between：两端对齐，项目之间的间隔都相等。
* space\-around：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。


![ justify-content](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129525-1553494924.gif)



> 对齐方式与轴的方向有关，本文中假设主轴从左到右。



```
.box {
   justify-content: start | end | flex-start | flex-end | center | left | right | space-between | space-around | space-evenly | stretch | safe | unsafe | baseline | first baseline | last baseline;
}

```

* **flex\-start（默认值）：左对齐**


![左对齐](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129496-1378684296.webp)


* **flex\-end：右对齐**


![右对齐](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129558-1419109638.webp)


* **center：居中**


![居中对齐](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129511-90523598.webp)


* **space\-between：两端对齐，项目之间间隔相等**


![两端对齐](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129523-1033601445.webp)


* **space\-around：每个项目两侧的间隔相等，即项目之间的间隔比项目与边框的间隔大一倍**


![两侧间隔相等](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129529-1476056105.webp)


### 4\.4、align\-items：定义在交叉轴上的对齐方式


align\-items 属性可以使元素在交叉轴方向对齐，它的初始值是 stretch，即拉伸到最高元素的高度。align\-items 属性有如下 5 个不同的值：


* flex\-start：交叉轴的起点对齐。
* flex\-end：交叉轴的终点对齐。
* center：交叉轴的中点对齐。
* baseline: 项目的第一行文字的基线对齐。
* stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。


![align-items](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129343-1905059603.gif)



> 对齐方式与交叉轴的方向有关，假设交叉轴从下到上。



```
.box{
    align-items: flex-start | flex-end | center | baseline | stretch;
}

```

* **flex\-start：起点对齐**


![起点对齐](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129570-759864833.webp)


* **flex\-end：终点对齐**


![终点对齐](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129461-792434172.webp)


* **center：中点对齐**


![中点对齐](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129534-214233364.webp)


* **baseline：项目的第一行文字的基线对齐**


![基线对齐](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129505-412438293.webp)


* **stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度**


![stretch（默认值）](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129486-1969581462.webp)


### 4\.5、align\-content：定义多根轴线的对齐方式


定义了多根轴线的对齐方式，如果项目只有一根轴线，那么该属性将不起作用


* flex\-start：与交叉轴的起点对齐。
* flex\-end：与交叉轴的终点对齐。
* center：与交叉轴的中点对齐。
* space\-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
* space\-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
* stretch（默认值）：轴线占满整个交叉轴。



> 如果项目只有一根轴线，该属性不起作用。
> 所以，容器必须设置flex\-wrap：···；



```
.box{
    align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}

```

* flex\-start：**与交叉轴的起点对齐**


![起点对齐](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129539-316404445.webp)


* flex\-end：**与交叉轴的终点对齐**


![终点对齐](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129268-1369140459.webp)


* center：**与交叉轴的中点对齐**


![中点对齐](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129560-256669987.webp)


* space\-between：**与交叉轴的两端对齐**，轴线之间的间隔平均分布


![轴线之间等间距](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129572-1260522678.webp)


* space\-around：**每根轴线两侧的间隔相等**，即轴线之间的间隔比轴线与边框的间隔大一倍


![轴线两侧等间距](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129573-911985823.webp)


* stretch（默认值）：**轴线占满整个交叉轴**。


![项目未设置高度时](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129559-1887897683.webp)


当你不给项目设置高度但是给容器设置align\-content不为stretch时，同一轴线上的项目的高度将等于项目中高度最高的项目。


![img](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129569-1860049269.webp)


### 4\.6、align\-content 和 align\-items 区别


* align\-items 适用于单行情况下，只有上对齐、下对齐、居中和 拉伸。
* align\-content适应于换行(多行)的情况下(单行情况下无效)，可以设置上对齐、下对齐、居中、拉伸以及平均分配剩余空间等属性值。
* 总结就是单行找 align\-items 多行找 align\-content。


![align-content 和 align-items 区别](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129571-63084245.webp)


## 5、项目属性（Item）



> 设置在项目上的属性也有6个。


* order
* flex\-grow
* flex\-shrink
* flex\-basis
* flex
* align\-self


![项目属性](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129555-1955217388.png)


### 5\.1、order属性：定义项目的排列顺序



> 数值越小，排列越靠前，默认为0，可以是负值。



```
.item {
    order: <整数>;
}

```

![order属性：定义项目的排列顺序](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129481-688170031.png)


### 5\.2、flex\-grow属性



> `flex-grow`属性定义项目的放大比例，默认为`0`，即如果存在剩余空间，也不放大。



```
.item{
    flex-grow: <数字>;
}

```

如果所有项目的`flex-grow`属性都为1，则它们将等分剩余空间（如果有的话）。如果一个项目的`flex-grow`属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍。


![flex-grow属性](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129499-1742941001.png)


### 5\.3、flex\-shrink属性


`flex-shrink`属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。



```
.item {
  flex-shrink: ; /* default 1 */
}

```

![flex-shrink属性](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129243-1234373014.jpg)


如果所有项目的`flex-shrink`属性都为1，当空间不足时，都将等比例缩小。如果一个项目的`flex-shrink`属性为0，其他项目都为1，则空间不足时，前者不缩小。


负值对该属性无效。


### 5\.4、align\-self属性


`align-self`属性允许单个项目有与其他项目不一样的对齐方式，可覆盖`align-items`属性。默认值为`auto`，表示继承父元素的`align-items`属性，如果没有父元素，则等同于`stretch`。



```
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}

```

![align-self属性](https://img2024.cnblogs.com/blog/157572/202411/157572-20241127103129568-1174099385.png)


看到这里，关于 Flex 布局的核心点就介绍得差不多了。掌握好这几个核心的知识点，再去实践练习基本上没有什么太大的问题。剩下一些比较小众的属性，等用到时再去查查看就是了。


## 6、参考资料


[弹性盒子\-https://developer.mozilla.org/zh\-CN/docs/Glossary/Flexbox](https://github.com)


[弹性盒布局\-https://developer.mozilla.org/zh\-CN/docs/Web/CSS/CSS\_flexible\_box\_layout/Basic\_concepts\_of\_flexbox](https://github.com)


[FlexTest\-https://flexbox.help/](https://github.com)


[Flex 布局教程：语法篇](https://github.com)


[Flexbox 布局的最简单表单](https://github.com):[wgetcloud全球加速服务机场](https://wa7.org)


[【保姆级教程】Vue项目调试技巧](https://github.com)


[干货\|工作中要使用Git，看这篇文章就够了](https://github.com)


[Vue 前端开发团队风格指南（史上最全）](https://github.com)


[企业数字化转型如何做？看过来](https://github.com)


[干货\-Vue3 组件通信方式详解](https://github.com)


[【长文】带你搞明白Redis](https://github.com)


