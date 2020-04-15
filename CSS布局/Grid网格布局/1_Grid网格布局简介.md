# Grid风格布局

> 资源来源于网络

> CSS 网格布局(Grid Layout) 是CSS中最强大的布局系统。
>
>  这是一个二维系统，这意味着它可以同时处理列和行，不像 [flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) 那样主要是一维系统。 
>
> 你可以通过将CSS规则应用于父元素（成为网格容器）和该元素的子元素（网格元素），来使用网格布局。




## 1. 引言

* CSS网格布局（又名“网格”）是一个二维的基于网格的布局系统，其目的只在于完全改变我们设计基于网格的用户界面的方式。
*  CSS一直用来布局网页，但一直都不完美。 
* 一开始我们使用table 做布局，然后转向浮动、定位以及inline-block，但所有这些方法本质上都是 Hack 的方式，并且遗漏了很多重要的功能（例如垂直居中）。 
* Flexbox的出现在一定程度上解决了这个问题，但是它的目的是为了更简单的一维布局，而不是复杂的二维布局（Flexbox和Grid实际上一起工作得很好）。 
* Grid是第一个专门为解决布局问题而生的CSS模块

* 雷切尔·安德鲁（Rachel Andrew）的书[为CSS Grid布局准备](http://abookapart.com/products/get-ready-for-css-grid-layout)。 这本书对网格布局做了彻底、清晰的介绍，也是是整篇文章的基础，我强烈建议你购买并阅读他的书。
*  我的另一个重要灵感是Chris Coyier的[Flexbox完全指南](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)，当需要查阅 flexbox 的一切资料时我就会找这篇文章。



--------

## 2. 基础知识以及浏览器支持情况

* 一开始你需要使用`display：grid`把容器元素定义为一个网格，使用`grid-template-columns`和`grid-template-rows`设置列和行大小，然后使用`grid-column` 和 `grid-row`把它的子元素放入网格。 
* 与flexbox类似，网格子元素的原始顺序不重要。 你的可以在 CSS 里以任意顺序放置它们，这使得使用媒体查询重新排列网格变得非常容易。 想象一下，我们需要定义整个页面的布局，然后为了适应不同的屏幕宽度完全重新排列，我们只需要几行CSS就能实现这个需求。 网格是有史以来最强大的CSS模块之一。

* 截至2017年3月，许多浏览器都提供了原生的、不加前缀的对CSS Grid的支持，比如 Chrome（包括Android），Firefox，Safari（包括iOS）和Opera。 另一方面，Internet Explorer 10和11支持它，但需要使用过时的语法。 Edge浏览器已经宣布将支持标准的Grid语法，但暂未支持
* 桌面浏览器:

| Chrome | Opera | Firefox | IE   | Edge | Safari            |
| :----- | :---- | :------ | :--- | :--- | :---------------- |
| 57     | 44    | 52      | 11*  | 16   | 10.1移动端 / 平板 |

* 移动端 / 平板

| iOS Safari | Opera Mobile | Opera Mini | Android | Android Chrome | Android Firefox |
| :--------- | :----------- | :--------- | :------ | :------------- | :-------------- |
| 10.3       | No           | No         | 62      | 62             | 57              |

> 在生产环境中使用Grid只是时间问题，但现在是我们该学习的时候了

-------
