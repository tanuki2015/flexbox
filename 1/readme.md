flex课程的案例

## basic
- 默认横排
- display: flux 沾满一行
- display： inline-flux 一行，内容的长度
- height: 100vh, 有高度的情况填充到高度范围
- 默认缩放， flex： 1 1 auto。

## direction
- 改变main cross方向
- item自动占满一行，犹如block元素

## wrap
- wrap的情况，一行摆不下自动换行
- nowrap，自动缩小或者出现滚动条

## order
- 默认0

## justify
- justify content对main axis 有效
- 改变main axis 为 column后， 高度为元素的实际高度
- 当min-height为100vh时，内容小于100vh时会是100vh
- 当main axis 为 column， justify content对应为 y axis

>这是要注意的地方，main axis改变， 对齐的方式跟着变。

## align items
- content 必须有高度， 否则不生效。
- 有高的content， 默认stretch整个content。

## align content
- items 默认填充content 高度，而align content需要多行
- 因此， 让items 的width 总和 大于一行， 给content加 wrap后， 可实现换行。
- 默认值是stretch。

## 可以发现，content 的每个属性都有默认值。
1. flex-direction: row;
2. flex-wrap: nowrap;
3. flex-flow: row, nowrap;
4. justify-content: flex-star;
5. align-items: stretch; 
6. align-content: stretch;

5,6同一时间只有一个起作用。

## items 属性
1. order default 0；
2. flex-grow default 0;如何分配一行的空余空间。
3. flex-shrink default 0; 
4. flex-basis default auto;
5. flex 简写上面三项。 auto | none
6. align-self default auto,继承父， 没有父 则 stretch.


## 几个更简单的技巧
1. flex-wrap: wrap 视口缩小时自动换行（当然换多少不可控）
2. item 使用 margin：auto； 自动居中（x,y,axis,神奇!!）


## aPage
1. 布局要成为弹性的，则不能设置如，width：1000px； 这种。但可以设置max-width：1000px；
2. img也需要设置width：100%, 否则不能弹性。
3. 在toggle一个nav的时候，.showNav要写在优先级高的媒体查询中，否则级别低了无效。