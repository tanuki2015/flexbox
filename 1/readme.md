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
