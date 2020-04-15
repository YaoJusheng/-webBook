# Flex基本概念

> 资源来源于网络

## 基本术语

* Flex容器(flex container):
  * 采用`flex`布局的元素, 称为`flex容器`, 简称**容器**
* Flex项目(flex item):
  * Flex容器中的所有成员(子元素)会自动成为该容器的成员,称为`flex项目`,简称**项目**
  * *flex项目都支持宽高设置, 哪怕它之前是内联元素,类似于浮动元素*

```html
<style>
  /*flex容器*/
  .contaier {
    display: flex;
  }
  /*flex项目*/
  .item {
    ...
  }
</style>
...
<div class="container">
  <span class="item">item1</span>
  <span class="item">item2</span>
  <span class="item">item3</span>
</div>
```

* 主轴(main axis): 
  * 也叫水平轴, 横轴,x轴
  * `main start`: 起始位置
  * `main end`: 结束位置
  * `main size`: 单个项目占据的主轴空间
* 交叉轴(cross axis):
  * 也叫垂直轴,坚轴,y轴
  * `cross start`: 起始位置
  * `cross end`: 结束位置
  * `cross size`: 单个项目占据的交叉轴空间

![术语](./images/bg2015071004.png)
