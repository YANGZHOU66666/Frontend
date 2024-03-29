# CSS布局

### \<div>盒子模型

![](D:/本科/Frontend/assets/box.jpg)

#### **重要结构属性：**

margin: 外边距

border: 边框

padding: 内边距

height: 高度

**width: **宽度

**width的其他值：**max-width——所有文字一直不换行的宽度；min-width——取文本中最长单词（以空格为分隔）产生的宽度

> 以上5个属性单位均为px

```css
margin: 1px;/*上下左右四个方向均为1px*/
margin: 1px 2px;/*上下->左右*/
margin: 1px 2px 3px;/*默认设置顺序：上->左右->下*/
margin: 1px 2px 3px 4px;/*上->右->下->左*/
margin: 0 auto;/*自动居中（上下0，左右auto，默认两边相同）*/
```

##### margin-left和left：

margin-left：相对左边元素，既可以是父元素，也可以是平级元素

left：只相对父元素左边距；如果是百分比，则是父元素content的值的百分比

#### **样式属性：**

```css
background-color: yellow; /*背景颜色*/
color:blue; /*文本颜色*/
font-size: 10px; /*文字尺寸，单位px，大小为文字高度；<mark>必须有单位</mark>*/
font-weight: 400; /*数字，正常400，加粗700（常用）；也可以用单词，正常normal，加粗strong*/
border: 3px solid black; /*三个属性：粗细、类型、颜色*/
border-radius: 3px; /*圆角*/
```

#### **float：**

不设置float的情形下，默认靠左，每新增一个盒子换一行

![](D:\本科\Frontend\notes\assets\float1_code.png)

![](D:\本科\Frontend\notes\assets\float1_img.png)

设置float的情况下：朝一个方向（左/右）对齐，如果一行不够则换行

![](D:\本科\Frontend\notes\assets\float2_code.png)

![](D:\本科\Frontend\notes\assets\float2_img.png)

某一个div不设置float: 不设置float的那个div后面换行，设置float的后面不换行

![](D:\本科\Frontend\notes\assets\float3_code.png)

![](D:\本科\Frontend\notes\assets\float3_img.png)

#### **overflow：**

如果父元素不够大导致子元素装不下，会导致溢出。这时候需要设置父元素的属性overflow. 

![](D:\本科\Frontend\notes\assets\overflow0.png)

**hidden值：**溢出的部分隐藏

![](D:\本科\Frontend\notes\assets\overflow1_code.png)

![](D:\本科\Frontend\notes\assets\overflow1_img.png)

**scroll值：**生成鼠标滑轮

![](D:\本科\Frontend\notes\assets\overflow2_code.png)

![](D:\本科\Frontend\notes\assets\overflow2_img.png)



### flex box模型

#### **将父元素设置为flex容器：**

```css
.c1{
    display: flex;
}
```

#### **默认：**

主轴(main axis)：横轴，从左向右为正方向

交叉轴(cross axis)：纵轴，从上向下为正方向

#### **flex-direction（用于设置主轴）属性的值：**

**row：**横向，从左到右为正方向

**row-reverse：**横向，从右到左为正方向

**column：**纵向，从上到下为正方向

**column-reverse：**纵向，从下到上为正方向

#### 设置flex模型的宽度（沿主轴方向的长度）

**默认宽度：max-content**，即让所有元素位于同一行（似乎当一行元素过于多时也不是这样，但是这在日常情况中应该碰不到，姑且这么认为）

（补充：上述括号内情形出现在一行会把父容器撑爆的情况，子容器内元素会换行）

![](D:\本科\Frontend\assets\flex_default.png)

![](D:\本科\Frontend\assets\flex_default_img.png)

**flex-basis：**设置初始宽度

注意：

1. 如果width-min大于flex-basis，那么该元素的宽度将会变成width-min而非flex-basis

2. 如果flex-basis设为0，那么宽度将会变成width-min

3. 如果对元素设置width为0，那么width会真的变为0（注意flex-basis和width的区别）

**flex-grow：**增长值，按照比例增长

所有元素的宽度之和填充整个容器主轴，增长的部分的比例是它们之间flex-grow值的比例

![](D:\本科\Frontend\assets\flex_width1_code.png)

![](D:\本科\Frontend\assets\flex_width1_img.png)

另：如果设置flex-basis为0，那么flex-grow的值的比例就会变为宽度的比例（width-min特别大的情况例外）

**flex-shrink：**与flex-grow类似，当flex-basis之和大于父元素宽度时，在本身值越大缩的越多，以保证刚好卡在父元素之间，但不低于width-min



#### 交叉轴对齐：align-items

stretch——将所有元素拉成父元素行高

![](D:\本科\Frontend\assets\flex_align_items1.png)

flex-start——按交叉轴的起点方向对齐

![](D:\本科\Frontend\assets\flex_align_items2.png)

flex-end——按交叉轴的终点方向对齐

![](D:\本科\Frontend\assets\flex_align_items3.png)

center——按交叉轴中点对齐

![](D:/本科/Frontend/assets/flex_align_items4.png)

baseline——文字基线对齐

![](D:/本科/Frontend/assets/flex_align_items5.png)

#### 主轴对齐：justify-content

**center**——中间对齐

![](D:\本科\Frontend\assets\flex_justify_content.png)

**flex-start，flex-end**分别对应靠近主轴起点、靠近主轴终点对齐，这里不放图片示范了

**space-around**——中间及两侧均有空隙，中间的空隙宽度是首位的两倍

![](D:\本科\Frontend\assets\flex_justify_content2.png)

space-evenly——中间及两侧均有空隙，空隙大小一样

![](D:\本科\Frontend\assets\flex_justify_content3.png)

**space-between**——两侧无空隙，中间有空隙

![](D:\本科\Frontend\notes\assets\flex_justify_content4.png)

#### 换行：flex-wrap

**wrap：**常规换行（这里满足每个元素的宽度为200px）

![](D:\本科\Frontend\notes\assets\flex_wrap1.png)

**wrap-reverse：**从下向上排列

#### 多轴之间的对齐：align-content

**flex-begin：**向交叉轴的起始对齐

![](D:\本科\Frontend\notes\assets\flex_align_content1.png)

**flex-end：**向交叉轴的结尾对齐

**space-around：**沿交叉轴分空隙对齐，首位有空隙且中间空隙是首尾两倍

**space-evenly：**沿交叉轴分均等空隙对齐，首位有空隙

**space-between：**首位无空隙

#### flex 排序：order

默认值为0，值越小越排在主轴的起始位置

![](D:\本科\Frontend\assets\flex_order1.png)

### position

#### static：

会随着文档流移动，不受top、bottom、left、right等属性影响

例：在上面加一行文字，或加一个盒子，static盒子均会沿着下移

![](D:\本科\Frontend\notes\assets\position_static.png)

#### absolute：

会被right、bottom、left、top等属性钉死在页面特定位置**（或父元素特定位置）**，会随着页面滚轮移动。注意absolute的元素会找上一个有定位的父元素，如果第一层父元素无定位，会再向上找

![](D:\本科\Frontend\notes\assets\position_absolute.png)

![](D:\本科\Frontend\notes\assets\position_absolute2.png)

注意：这里的right、left等属性是相对它的父级元素定位的

#### relative：

随文档流移动，但可以设置上下左右，随其它元素移动而变化

![](D:\本科\Frontend\assets\position_relative.png)

#### fixed：

类似absolute，但滑动页面它不移动

![](D:\本科\Frontend\assets\position_fixed.png)

在relative的父元素中设置fixed的子元素：该子元素会定在relative的左上角；但一旦声明了fixed元素的上下左右等坐标，就会脱离relative的束缚

#### sticky：

正常情况下应该等同于static（？）

页面下滑至sticky贴在顶部时，sticky会在顶部一直贴着（如果设置top、left等属性，贴在顶部时会受这些影响）