# CSS学习笔记
   * [CSS学习笔记](#css学习笔记)
      * [一、对css的初印象](#一对css的初印象)
      * [二、css的引入方式](#二css的引入方式)
      * [三、css之选择器](#三css之选择器)
         * [3.1 基础选择器](#31-基础选择器)
      * [四、css字体属性](#四css字体属性)
         * [4.1 字体样式](#41-字体样式)
         * [4.2 字体大小](#42-字体大小)
         * [4.3 字体粗细](#43-字体粗细)
         * [4.4 文字样式](#44-文字样式)
         * [4.5 复合属性（字体属性的简写方法）](#45-复合属性字体属性的简写方法)
      * [五、css文本属性](#五css文本属性)
         * [5.1 文本颜色](#51-文本颜色)
         * [5.2 对齐文本](#52-对齐文本)
         * [5.3 装饰文本](#53-装饰文本)
         * [5.4 文本缩进](#54-文本缩进)
         * [5.5 行间距](#55-行间距)
      * [六、css背景](#六css背景)
         * [6.1 背景颜色](#61-背景颜色)
         * [6.2 背景图片](#62-背景图片)
         * [6.3 背景平铺](#63-背景平铺)
         * [6.4 背景图片的位置](#64-背景图片的位置)
         * [6.5 背景图像的附着](#65-背景图像的附着)
         * [6.6 背景的复合写法](#66-背景的复合写法)
      * [七、css的盒子模型](#七css的盒子模型)
         * [7.1 border边框](#71-border边框)
         * [7.2 盒子的内边距padding](#72-盒子的内边距padding)
         * [7.3 盒子的外边距margin](#73-盒子的外边距margin)
      * [八、css的浮动](#八css的浮动)
         * [8.1 对浮动的理解](#81-对浮动的理解)
         * [8.2 css浮动的特性](#82-css浮动的特性)
         * [8.3 css浮动技巧之搭配标准流父级](#83-css浮动技巧之搭配标准流父级)
         * [css浮动之清除浮动](#css浮动之清除浮动)
      * [九、小技巧之如何简单测量盒子的宽度以及高度](#九小技巧之如何简单测量盒子的宽度以及高度)
      * [十、传统网页布局的方式](#十传统网页布局的方式)
      * [十一、小技巧之如何从网站上抠图片下来](#十一小技巧之如何从网站上抠图片下来)
   * [参考资料](#参考资料)

## 一、对css的初印象

css的中文全称是层叠式样式表，也被称为css样式表或者级联式样式表

它的主要目的是美化HTML的页面，是版面样式和布局更加美观。

**总体的结构总的来说即为:** `将要被改样式的目标 { 将其改为什么样式 }`

**小tip:** 每一个属性的结尾都要加入分号



## 二、css的引入方式

1. **内部样式表**

   **标签命名方式:** `<style> 选择器{放置各种属性} </style>`

   将css的代码放在标签`<style></style>`中，然后将这个整体放入HTML代码的head中（但是其实可以将style标签放在HTML代码中的任意一个地方，但是为了方便阅读，因此统一将style放在head标签里面。）

   控制范围是当前存在的HTML页面

2. **行内样式表**

   **标签命名方式:** `<将要该改变的目标标签 style="放置css属性">`

   **PS:** 对于单个或者较少的段落需要css简单的修饰，则采用此种方式

3. **外部样式表（重点）**

   适用于样式比较多的情况，将样式单独写入css文件中，之后将css文件引入到HTML页面中使用。

   1. 首先，先新建一个后缀名为.css的样式文件，将所有css代码都放入样式文件中。

   2. 在这个样式文件中无需写style标签，直接`选择器{放置各种属性}`

   3. 在head标签中使用link标签引入css

      **link标签中需要定义两个属性**

      - rel，当前文件和被链接文件之间的关系，目前学到的只有指定为“stylesheet”，表示被链接的文档是一个样式表文件。

      - herf，填写所要链接的外部样式表文件的路径（可以用相对路径，也可以用绝对路径，推荐练习相对路径）。

   

## 三、css之选择器

### 3.1 基础选择器

* **标签选择器**

  将标签名（不用加<>）作为选择器

  它的优点是可以把同类型的标签全部统一设置，但是这同样也是它的缺点，无法对同一类型的标签进行不同的设置

* **类选择器**

  可以单独选择一个或者某几个标签，同时这些标签可以是不同类的

  使用方法：

  1. 使用专用的class属性为将要改变的标签命名`<将要改变的标签 class="所命名的名字">`

  2. 需要用`.命名的名字`后面再改变样式就可以了

     有专业的类命名规则可以去学习，或者命名时尽量使用英文（实在不行拼音），并使它有一定的意义。

     **PS：**类选择器还有可以使用多命名的方式，只要记得将命名多个命名一同放在class属性中即可，这样做的优点是可以对不同的样式进行清晰的分类

* **id选择器**

  **语法格式:** 以＃号后面填写id属性

  其弊端在于id选择器只可以调用一次，无法和类选择器一样可以使用多次

* **通配符选择器**

  通过`*`一次性定义页面中所有的HTML标签



## 四、css字体属性

### 4.1 字体样式

**标签命名方式:** `选择器{font-family:"字体"；}`

字体可以使用中文，但是最好使用其对应的英文（可以让它的兼容性更加的优秀）

**PS:**  **最好使用比较通用的字体，不要使用比较小众的字体，否则可能这种字体在其他用户的浏览器上可能无法正常显示。**

**如果同时有多个字体，需要使用逗号隔开，由多个单词拼成的字体英文名最好使用引号进行包含，单引号和双引号都可以。**



### 4.2 字体大小

**标签命名样式:** `选择器{font-size: 所需字体大小；}`

需要带单位px（像素），而且**单位和数值之间不能带空格**，要连在一起

因为在不同的浏览器上可能默认的字体大小不同，因此统一字体大小有利于效果的展示

**可以直接指定body来式整个页面中的字体改变，但是body中的有h标签的字体是无法被这样改变的，需要单独指定大小**



### 4.3 字体粗细

**标签命名样式:** `选择器{font-weight: 字体的粗细；}`

可以使用单词normal，bold，lighter，但是同样可以使用数字来代替单词

随着数字的增大（减小），字体的粗细也发生相应的变粗（变细），400代表normal数值



### 4.4 文字样式

**标签命名样式:** `选择器{font-style: 样式名称；}`

有默认的样式normal以及斜体italic样式

不过有`<em>`和`<i>`标签可以使文字变为斜体，因此这个属性并不常用



### 4.5 复合属性（字体属性的简写方法）

**标签命名样式:** `选择器{font: 按顺序填写所需的属性值即可；}`

**tip: 填写属性值需要遵循一定的顺序**

font-style	font-variant	font-weight	font-size/line-height	font-family

不能更改顺序，必须严格遵守，可以省略部分属性，但是必须填写font-size和font-family属性，否则font属性将不起作用

各个属性值之间要用逗号隔开



## 五、css文本属性

### 5.1 文本颜色

**语法规范:** `选择器{color: 填写相关颜色属性值；}`

**颜色属性值的表示方式有很多:** 

- 已经预定义的颜色值，即相关颜色的英语单词表示
- 通过相应属性值的十六进制来表示
- 通过相应的RGB代码格式来表示，这个更加方便，可以在随意输入一个rgb格式的颜色以后，将光标停在出现的颜色块上，即可随意的选择各种颜色效果



### 5.2 对齐文本

**语法规范:** `选择器{text-align: 对齐方式的属性值；}`

**PS:** 只能用于设置元素内文本内容的水平对齐方式



### 5.3 装饰文本

**语法规范:** `选择器{text-decoration: 对文本的修饰方式；}`

**修饰的方式:**

* none，默认无装饰
* underline，下划线
* overline，上划线
* line-through，删除线

一般最常用的是取消创建的链接的下划线，即使用none，其他的基本不常用



### 5.4 文本缩进

**语法规范:** `选择器{text-indent: 对文本缩进的大小；}`

文本使用如果为规定正负号，则默认为缩进，缩进的大小规定单位可以使用像素（px），但是最常用的缩进单位是一个文字大小（em）



### 5.5 行间距

**语法规范:** `选择器{line-hight: 对文字的行间的距离的设置；}`

**对于行间距的理解:** 行间距=文字的高度+上间距+下间距

行高同样需要使用单位像素（px）



## 六、css背景

### 6.1 背景颜色

**语法规范:** `选择器{background-color: 需要的背景颜色；}`

颜色的颜色值可以类比字体颜色

**PS:** 背景颜色的默认值一般是transparent（透明）



### 6.2 背景图片

**语法规范:** `选择器{background-image: url（插入的图片的地址）；}`



### 6.3 背景平铺

**语法规范:** `选择器{background-repeat: 对于背景的平铺方式的选择；}`

**平铺属性可以选择的参数:**

* no-repeat，不平铺
* repeat，平铺
* repeat-x（y），沿着x（y）轴平铺



### 6.4 背景图片的位置

**语法规范:** `选择器 {background-position: x y（描述x轴和y轴的显示位置）；}`

**参数值的方位名词的选择:**

|  x轴   |  y轴   |
| :----: | :----: |
|  top   |  left  |
| center | center |
| bottom | right  |

**参数值的精确单位：填写数值和单位px**

意义是图片相对x轴和y轴的距离

**PS:** 可以使用混合单位，即将方位名词和精确单位混合使用

虽然方位名词可以颠倒使用，但是为了使意义更加明确并且不让坏习惯影响精确单位输入和混合单位输入，因此要严格遵守先x后y才可以。



### 6.5 背景图像的附着

**语法规范:** `选择器 {background-attachment: 选择是图像固定还是随对象内容滚动；}`

* scroll，背景图像随内容滚动而滚动
* fixed，虽然内容在滚动，但是背景图像固定



### 6.6 背景的复合写法

**语法规范:** `选择器 {background-attachment: 填写所需的属性值；}`

这个简写属性不同于字体的简写，它没有特定的书写顺序。

**但是为了使意思更加一目了然，依然有习惯约定的顺序：**

背景颜色	地址	平铺	是否滚动	位置



## 七、css的盒子模型

在初步学习过HTML和css以后，对于网页的布局变得更加的敏感，一个完整的网页大多都是由一块一块的区域构成，每一块区域都可以看作是一个盒子，网页的布局即为向盒子中装所需的网页元素，设计好它的样式，并且将盒子摆放着一个适合的位置即可。

css的盒子模型的本质就是对目标HTML元素进行封装



### 7.1 border边框

* border-width，定义边框的粗细，单位是px

* border-style，[边框的样式](https://www.runoob.com/css/css-border.html)

  **PS：**样式中一些比较花哨的样式兼容性比较差，简单一点的比较靠谱

* border-color，更改边框的颜色

  **PS:** 和字体的颜色使用语法规则相同

同样边框也有简写（复合）方式：`选择器 {border: 填写所需的属性值；}`

**PS:** 这些那个属性值之间没有顺序

可以通过使用`border-方位名词：所需属性值；`来控制不同位置的边框的样式

对于同一个目标的指令，下一条指令可以覆盖上一条指令中相同的属性。

* border-collapse：collapse，表示相邻的边框合并

  目的是为了使表格的内部边框不因为重叠而变粗显得视觉上不协调

**tip:** 盒子在测量的时候要注意边框的宽度会加宽盒子的宽度



### 7.2 盒子的内边距padding

**语法规范:** `选择器 {padding-方位名词: 填写所需的属性值；}`

同样可以通过复合写法综合各个方位

**语法规范:** `选择器 {padding: 填写所需的属性值；}`

属性值的填写按照顺时针，上，右，下，左

**其实还有填写一个、两个、三个值的情况，都有各自的特殊意义**

- 一个值，上下左右控制

- 两个值，上下，左右分别控制

- 三个值，上，左右，下，分别控制

**PS:** 内边距同样会影响盒子的宽度



### 7.3 盒子的外边距margin

**语法规范:** `选择器 {margin-方位名词: 填写所需的属性值；}`

它的复合写法和意义和padding完全一样



## 八、css的浮动

**相应的语法规范:** `选择器 {float: 填写所需的属性值；}`

**其属性值包含以下三个:**

* none，元素不浮动
* left，元素向左浮动
* right，元素向右浮动



### 8.1 对浮动的理解

浮动属性主要用于创建浮动框，此时的浮动框将会做出相应的指示行动，直到行动到触及左边缘或右边缘或者另一个浮动框的边缘以后，浮动框将会结束相应的指令行动。



### 8.2 css浮动的特性

1. 浮动的元素会脱离标准流的控制，移动到指定的位置
2. 浮动的元素移动后，原来的位置将不再存在，后面的标准流元素将自动填满浮动元素的位置。
3. 多个浮动元素会自动变为一行内进行显示，当屏幕界面变小无法容纳完整的一行盒子，即当前屏幕的宽度无法装下一整行盒子时，多出来的盒子会自动另起一行。



### 8.3 css浮动技巧之搭配标准流父级

**使用背景:** 由于在一些场景中，需要两个css的浮动框同时存在于整个HTML页面的顶部中央整齐排列，但是浮动只有左浮动或右浮动或者不动，因此无法达到所需的效果，所以出现了这种方法。

**完成此效果的方法:**

1. 制作一个空盒子div，并设置它与所需的浮动框相同的高度，宽度为两个浮动框的和
2. 通过css的修饰，将空盒子的位置设置为顶部居中
3. 接着在这个空盒子中添加两个向左或向右浮动的浮动框即可完成预期的效果

**经过思考，我想到的此技巧的替代方法:**

1. 先量出界面中所需的浮动盒子距离边框的白色宽度记为x
2. 创建一个白色的，高度与“将要处于整个HTML界面顶部中央的盒子”一样高向左浮动的盒子宽度为x
3. 再创建两个“将要处于整个HTML界面顶部中央整齐排列的盒子”即可同样完成所需的效果



### css浮动之清除浮动

**此方法的应用背景:**

在真正的网页制作中，对于一个盒子，如果为它设定了固定的高度和宽度属性，那么如果以这个盒子为模板，则在未来的网页制作中，一旦出现了内容超出盒子范围的情况，那么，内容的显示将出现问题。

此时就需要一个可以随着内容的改变而自由的更改高度盒子。

第一个想法是不为盒子设定高度，通过内部的内容增添自动撑开盒子。但是由于内部需要一个个小的浮动盒子为模板，在内部的盒子设置为浮动以后，原来的大盒子的高度就自动的变为了零。

**方法:**

1. **额外标签法**

   通过在最后所有浮动框的最后面加入一个空的标签

   可以使用过`<div style="clear:both"></div>`

   **tip:** 要求新添加的标签必须是块级元素，不能是行内元素

2. **父级添加overflow属性**

   语法格式一般为overflow：hidden或者auto或者scroll；

3. **父级添加after伪元素**

4. **父级添加双伪元素**

   **PS:** 由于时间的限制，后面的两种方式仅仅是进行了了解，未能进行深度的学习。



## 九、小技巧之如何简单测量盒子的宽度以及高度

通过屏幕的截屏功能即可实现，在截屏时通过矩形截屏框框选所要测量的盒子，会在截屏界面的右上方出现所框选区域的”宽度x高度“的像素值，这样在创建盒子时就可以通过css来设置相关盒子的宽度及高度属性。



## 十、传统网页布局的方式

**通过css来摆放盒子**

1. **标准流（普通流，文档流）**

   即块级元素和行内元素按照默认的顺序排列的方式

2. **浮动**

   在网页布局中经常会采取通过标准流的父元素排列上下位置，之后内部的子元素采取浮动排列左右位置这样的网页布局方式

3. **定位**

   

## 十一、小技巧之如何从网站上抠图片下来

打开网站的源代码界面，通过“在页面选择一个元素进行检查”选中想要的图片，从style中找到它的图片链接地址，右键，点击open in new tab，即可找到图片，接着”另存为“即可完成抠图。



---



# 参考资料

- [菜鸟教程之css学习](https://www.runoob.com/css/css-tutorial.html)
