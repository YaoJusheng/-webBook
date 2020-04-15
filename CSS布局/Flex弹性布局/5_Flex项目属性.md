> 资源来源于网络

# Flex项目属性

巧合的是, 在Flex项目也有6个可用的属性,他们分别是:

| 序号 | 属性        | 描述                                                         |
| ---- | ----------- | ------------------------------------------------------------ |
| 1    | order       | 定义项目排列顺序,索引越小超靠前,默认为0                      |
| 2    | flex-grow   | 定义项目的放大比例,默认为0表示不放大, 即就算存在剩余空间也不放大 |
| 3    | flex-shrink | 定义了项目的缩小比例,默认为1,即如何空间不足,则自动缩小项目来填充 |
| 4    | flex-basis  | 定义了项目占据的主轴空间,默认值为auto, 即项目原始大小        |
| 5    | flex        | 是flex-grow,flex-shrink,flex-basis简写,默认值: 0 1 auto, 后二个属性可选 |
| 6    | align-self  | 个性化定定制某单个项目的对齐方式,可覆盖容器`align-items`属性,默认auto |

---

## 1. order

* 定义项目的排列顺序。数值越小，排列越靠前，默认为0
* CSS语法:

```css
.item {
  order: integer;
}
```

* 示意图:

![order](./images/bg2015071013.png)

---

## 2. flex-grow

* 设置项目的放大比例, 默认为0: 不放大,哪怕轴上有剩余空间
* CSS语法:

```css
.item {
  flex-grow: number; /* default: 0 */
}
```

* 空间分配方案小案例:
  * `flex-grow: 1`: 每个项目等分, 都占全部的空间的N分之一(N: 项目数量)
  * `flex-grow: 2`如果某个项目为2, 其它项目为1, 则它占据空间比其它项目多一倍

![flex-grow](./images/bg2015071014.png)

---

## 3. flex-shrink

* 设置了项目的缩小比例,默认为1, 即空间不足时, 自动缩小填充
* CSS语法:

```css
.item {
  flex-shrink: number; /*defautl: 1*/
}
```

* 缩放规则
  * `flex-shrink: 1`: 所有项目都为1, 空间不足时, 自动等比例缩小填充主轴剩余空间
  * `flex-shrink`: 如果有一个项目为0, 其它项目为1, 则空间不足时, 它并不随其它项目缩小
  * 注意: 该属性不支持负值, 即`flex-shrink: -1` 无效

![flex-shrink](./images/bg2015071015.jpg)

---

## 4. flex-basis

* 定义了在计算分配主轴上剩余空间之前, 项目占据的主轴空间(main size)
  * 浏览器根据该属性,可以计算出主轴上是否还有剩余空间, 决定是否换行
  * 默认值为`auto`, 即项目原来占据的空间大小
* CSS语法:

```css
.item {
  flex-basis: length | auto; /* default auto */
}
```

你可以设置与`height`或者`width`属性一样的绝对值,例如`500px`,则该项目占据固定的空间大小

```css
.item {
  flex-basis: 500px;
}
```

---

## 5. flex

* flex属性是前面`flex-grow`,`flex-shrink`和`flex-basis`属性的简写
* 默认值: `0  1 auto`, 除第一个外, 其它二个可选
* CSS语法:

```css
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
}
```

* 由于该属性极其常用, 为了简化, Flex布局还为该属性设置了快捷值
  * `flex: auto`:  等价于`flex: 1 1 auto`
  * `flex: none`: 等价于`flex: 0 0 auto`
* 推荐优先使用flex属性, 由浏览器自动计算出其它属性的值

---

## 6. align-self

* 该属性允许单个项目有与其它项目不一样的对齐方式, 可覆盖掉容器的`flex-items`属性
* 默认值: `auto`,表示继承父元素的`align-items`,如果没有父元素,则等价于`stretch`
* CSS语法:

```css
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

* 示意图:

![align-self](./images/bg2015071016.png)

