# flex layout

html:
```
 <body>
    <div id="wrapper">
      <div class="box-1">
        <h3>box one</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit</p>
      </div>
      <div class="box-2">
        <h3>box two</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit</p>
      </div>
      <div class="box-3">
        <h3>box three</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit</p>
      </div>
    </div>
  </body>
```

css:
```
<style>
      #wrapper {

      }
      #wrapper div{
        border: 1px #ccc solid;
        padding: 10px;
      }
      .box-1{
        
      }
      .box-2{

      }
      .box-3{

      }
    </style>
```

如上所示，默认文档流，沿 y axis 向下

## question1： 如何变成 x axis 排列？

answer： 给容器设置flex属性
`display: flex;`

## q2: 想让box-1占据一半的空间？

a: 设置box-1的flex-grow的值为 0~n

0表示不缩放，如果都为1则等于默认效果

如果其中一个为2，则站位空间为其他的两倍。

简写为 `flex：2`

## q3: 改变order？

a: 给每个box设置 `order`值， 1~n， 则按顺序排列

## q3: boxd的沿cross axis对齐方式 

a: 在容器设置align-item:
```
#wrapper {
  align-items: flex-start | flex-end | center | baseline | stretch;
}
```

## q4: 让box沿着main cross 排列

a: 在容器设置flex-direction为 column

## q5: 让box沿 main cross 对齐 

a: 首先要让box的宽度小于容器，这样才有空间 `width: 30%`
每个30%，还剩10%。

然后，在容器设置justify-content,
`  justify-content: flex-start | flex-end | center | space-between | space-around;`

### dice 案例
一个dice可以放置做多9个点。

#### 4个色子的问题
<s>1. 容器是block的情况下，里面的块元素从上到下依次排列，沾满整行。
2. 设置为flex后，子元素变成水平排列。 而且根据自身的宽度沾满了 y axis。
3. 分开两列： `justify-content: space-between;
4. 现在每一列中的两个色子是标准流的位置，我们需要做的是让他的子元素（两个点），沿着x axis排列：
    * 所以第一步是要把容器变成flex,这样子元素就变成横排了。</s> 
`
这个问题有点嚼劲。

##### tips：其实关键在于，我们需要让flex中的子元素独自沾满整行，就像在标准流中一样。
所以：
1. 子元素用basis占据主轴100%位置。
2. 要设置wrap使其换行。

有了上面的基础后，才能使用align-content这个多行对齐的属性。

最后让子元素也成为flex，然后让他的子元素justify对齐就行了

mark一下：代码中的column应该是row才对