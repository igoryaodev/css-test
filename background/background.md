**`background`** 是一种 [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) 简写属性，用于一次性集中定义各种背景属性，包括 color, image, origin 与 size, repeat 方式等等。

> 标准语法

```
[ <bg-layer> , ]* <final-bg-layer>
where 
<bg-layer> = <bg-image> || <bg-position> [ / <bg-size> ]? || <repeat-style> || <attachment> || <box> || <box>
<final-bg-layer> = <'background-color'> || <bg-image> || <bg-position> [ / <bg-size> ]? || <repeat-style> || <attachment> || <box> || <box>

where 
<bg-image> = none | <image>
<bg-position> = [ [ left | center | right | top | bottom | <length-percentage> ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ] | [ center | [ left | right ] <length-percentage>? ] && [ center | [ top | bottom ] <length-percentage>? ] ]
<bg-size> = [ <length-percentage> | auto ]{1,2} | cover | contain
<repeat-style> = repeat-x | repeat-y | [ repeat | space | round | no-repeat ]{1,2}
<attachment> = scroll | fixed | local
<box> = border-box | padding-box | content-box

where 
<image> = <url> | <image()> | <image-set()> | <element()> | <cross-fade()> | <gradient>
<length-percentage> = <length> | <percentage>

where 
<image()> = image( <image-tags>? [ <image-src>? , <color>? ]! )
<image-set()> = image-set( <image-set-option># )
<element()> = element( <id-selector> )
<cross-fade()> = cross-fade( <cf-mixing-image> , <cf-final-image>? )
<gradient> = <linear-gradient()> | <repeating-linear-gradient()> | <radial-gradient()> | <repeating-radial-gradient()> | <conic-gradient()>

where 
<image-tags> = ltr | rtl
<image-src> = <url> | <string>
<color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>
<image-set-option> = [ <image> | <string> ] <resolution>
<id-selector> = <hash-token>
<cf-mixing-image> = <percentage>? && <image>
<cf-final-image> = <image> | <color>
<linear-gradient()> = linear-gradient( [ <angle> | to <side-or-corner> ]? , <color-stop-list> )
<repeating-linear-gradient()> = repeating-linear-gradient( [ <angle> | to <side-or-corner> ]? , <color-stop-list> )
<radial-gradient()> = radial-gradient( [ <ending-shape> || <size> ]? [ at <position> ]? , <color-stop-list> )
<repeating-radial-gradient()> = repeating-radial-gradient( [ <ending-shape> || <size> ]? [ at <position> ]? , <color-stop-list> )
<conic-gradient()> = conic-gradient( [ from <angle> ]? [ at <position> ]?, <angular-color-stop-list> )

where 
<rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
<rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
<hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
<hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )
<side-or-corner> = [ left | right ] || [ top | bottom ]
<color-stop-list> = [ <linear-color-stop> [, <linear-color-hint>]? ]# , <linear-color-stop>
<ending-shape> = circle | ellipse
<size> = closest-side | farthest-side | closest-corner | farthest-corner | <length> | <length-percentage>{2}
<position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]
<angular-color-stop-list> = [ <angular-color-stop> [, <angular-color-hint>]? ]# , <angular-color-stop>

where 
<alpha-value> = <number> | <percentage>
<hue> = <number> | <angle>
<linear-color-stop> = <color> <color-stop-length>?
<linear-color-hint> = <length-percentage>
<angular-color-stop> = <color> && <color-stop-angle>?
<angular-color-hint> = <angle-percentage>

where 
<color-stop-length> = <length-percentage>{1,2}
<color-stop-angle> = <angle-percentage>{1,2}
<angle-percentage> = <angle> | <percentage>
```



> background`(简写形式)`

![image.png](https://upload-images.jianshu.io/upload_images/12041061-6dfa25f623a3ccfd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/620)
```
语法：
background: <bg-layer>, <bg-layer>,....; #background: 最上一层，....， 最下一层

# background: color image position / size repeat-style attachment box box; // color >> final-layer
# background:  url() left(x) bottom(y) / 20%(width) 50%(height) no-repeat local border-box border-box,  
background:  
url() left bottom / 20% 50% no-repeat local border-box border-box,  
url() 10% 30% / 50% 50% no-repeat local content-box border-box,  
  ...
green  url() left 50% / 50% 50%  no-repeat  local border-box border-box; 


#background  demo
   .base{
      width: 200px;
      font-size: 12px;
      height: 200px;
      border: 2px solid #fff;
      float: left;
      margin-right: 10px;
      margin-top: 10px; 
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 10px;
      box-sizing: border-box;
    }
.demo{
  background:  
        url(https://upload-images.jianshu.io/upload_images/12041061-95393ded037c7fb5.jpg) left 15%/20% 40% no-repeat local border-box content-box, /*6 最上层图(眼珠)*/
        url(https://upload-images.jianshu.io/upload_images/12041061-f40c4e55bcdd1e86.png) right center / 100% auto no-repeat local content-box content-box, /*5  中间图(图标列表) 设置content-box 被裁剪*/
        url(https://upload-images.jianshu.io/upload_images/12041061-f40c4e55bcdd1e86.png) right top / 100% auto no-repeat local border-box border-box, /*4  中间图(图标列表)*/
        url(https://upload-images.jianshu.io/upload_images/12041061-f40c4e55bcdd1e86.png) right bottom / 100% auto no-repeat local border-box content-box, /*3  中间图(图标列表) 被裁剪*/
        url(https://upload-images.jianshu.io/upload_images/12041061-1b34cb94b686e162.png) 80% 20%/ 30% auto no-repeat local border-box border-box, /* 2 中间图(蜥蜴)*/
        radial-gradient(green, skyblue); /* 1 最底层*/
}
<div class="base demo"></div>
```

![background demo](https://upload-images.jianshu.io/upload_images/12041061-ccc0c0dd2dc5bd2a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> <bg-layer> 背景层`(最底层可以设置背景颜色)`

```
<bg-layer>:<bg-color> <bg-image> <bg-position> <bg-size> <repeat-style> <attachment> <box> <box>; # <bg-color> 仅适用于最底层

#<bg-layer> = background-color background-image background-position 
background-size background-attachment background-origin background-clip
# url() left(x) bottom(y) / 20%(width) 50%(height) no-repeat local border-box border-box,  
#<bg-layer> 背景色 背景图 背景位置 背景尺寸 背景悬浮方式 背景附加内容框 背景边框

```

> background-attachment CSS 属性决定背景图像的位置是在视口内固定，还是随着包含它的区块滚动。

```
fixed
此关键字表示背景相对于视口固定。即使一个元素拥有滚动机制，背景也不会随着元素的内容滚动。
local
此关键字表示背景相对于元素的内容固定。如果一个元素拥有滚动机制，背景将会随着元素的内容滚动， 并且背景的绘制区域和定位区域是相对于可滚动的区域而不是包含他们的边框。
scroll
此关键字表示背景相对于元素本身固定， 而不是随着它的内容滚动（对元素边框是有效的）。
```

> background-clip  设置元素的背景（背景图片或颜色）是否延伸到边框下面。

![background-clip](https://upload-images.jianshu.io/upload_images/12041061-5dd674b782c08171.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

```
如果没有设置背景图片（background-image）或背景颜色（background-color），那么这个属性只有在边框（ border）被设置为非固实（soild）、透明或半透明时才能看到视觉效果（与 border-style 或 border-image 有关），否则，本属性产生的样式变化会被边框覆盖。
border-box
背景延伸至边框外沿（但是在边框下层）。
padding-box
背景延伸至内边距（padding）外沿。不会绘制到边框处。
content-box
背景被裁剪至内容区（content box）外沿。
text 
背景被裁剪成文字的前景色。
```

> background-origin 规定了指定背景图片background-image 属性的原点位置的背景相对区域.`注意：当使用 background-attachment 为fixed时，该属性将被忽略不起作用。`

```
 border-box
背景图片的摆放以border区域为参考
padding-box
背景图片的摆放以padding区域为参考
content-box
背景图片的摆放以content区域为参考
```

> background-position 为每一个背景图片设置初始位置。 这个位置是相对于由 background-origin 定义的位置图层的。`background-position 属性被指定为一个或多个 <position> 值，用逗号隔开`

```
background-position: left;
background-position: center;
background-position: 25% 75%;
background-position: bottom 50px right 100px;

```
```
关键字 center，用来居中背景图片。
关键字 top, left, bottom, right 中的一个。用来指定把这个项目（原文为 item）放在哪一个边缘。另一个维度被设置成 50%，所以这个项目（原文为 item）被放在指定边缘的中间位置。
<length> 或 <percentage>。指定相对于左边缘的 x 坐标，y 坐标被设置成 50%。
如果一个值是  top 或  bottom，那么另一个值不应该是 top 或 bottom。
如果一个值是  left 或   right，那么另一个值不应该是 left 或 right 。
+50px（将图片的左边界对齐容器的中线）
0px（图片的左边界与容器左边界重合）
-100px（将图片相对容器左移100px，这意味着图片中部的100px内容将出现在容器中）
-200px（将图片相对容器左移200px，这意味着图片右部分的100px内容将出现在容器中）
-250px（将图片相对容器左移250px，这意味着图片的右边界对齐容器的中线）
    另外需要注意，如果背景图片的大小和容器一样，那设置百分比的值将永远无效，因为“容器和图片的差”为0（图片永远填满容器，并且图片的相对位置和容器的相对位置永远重合）。在这种情况下，需要为偏移使用绝对值（例如px）。

<position>
  一个 <position> 定义一组 x/y 坐标（相对于一个元素盒子模型的边缘），来放置这个项目（原文为 item）。它可以被定义为一个值或者两个值。如果被定义为两个值，那么第一个值代表水平位置，第二个代表垂直垂直位置。如果只指定一个值，那么第二个值默认为 center。
一个值的语法: 这个值可以是：

两个值的语法: 一个定义 x 坐标，另一个定义 y 坐标。每个值可以是：

关键字 top, left, bottom, right 中的一个。 如果这里给出 left 或 right，那么这个值定义 x 轴位置，另一个值定义 y 轴位置。如果这里给出 top 或  bottom，那么这个值定义 y 轴位置，另一个值定义 x 轴位置。
<length> 或 <percentage>。如果另一个值是  left 或  right，那么这个值（指 <length> 或 <percentage>）定义相对于上边缘的 y 轴位置。 如果两个值都是 <length> 或 <percentage>，那么第一个值定义 x 轴位置，第二个定义 y 轴位置。
注意：

也就是说，top top 和 left left 是无效的。

至于百分比：

百分比值的偏移指定图片的相对位置和容器的相对位置重合。值0%代表图片的左边界（或上边界）和容器的左边界（上边界）重合。值100%代表图片的右边界（或下边界）和容器的右边界（或下边界）重合。值50%则代表图片的中点和容器的中点重合。

当指定百分比值的时候，实际上执行了以下的计算公式（该公式可以用数学方式定义图片和容器相对位置重合）：

(container width - image width) * (position x%) = (x offset value)
(container height - image height) * (position y%) = (y offset value)

使用X坐标来举个例子，假设有一个300px宽的图片，将这个图片使用到一个100px宽的容器中，并且将background-size设置成自动：

100px - 300px = -200px (容器和图片的宽度差)

当对background-position设置值依次为-25%，0%，50%，100%，125%，得到图片相对容器的偏移值为：

-200px * -25% = 50px
-200px * 0% = 0px
-200px * 50% = -100px
-200px * 100% = -200px
-200px * 125% = -250px

对于这些例子中设置的偏移，图片相对容器真实的偏移值就是：
```

> background-position-x CSS 属性设置水平方向的位置，与每个背景图片等位置层设置属性 background-origin相关。更多信息请查看background-position属性，这个用的比较普遍。

> background-position-y 属性用于设置初始状态时背景图片在垂直方向上的位置,这个位置相对于通过 background-origin 定义的背景层的原点进行定位. 需要获得更多的信息可以查看background-position 属性,这个属性已经得到了长久且广泛的支持.

>background-repeat CSS 属性定义背景图像的重复方式。背景图像可以沿着水平轴，垂直轴，两个轴重复，或者根本不重复。`默认情况下，重复的图像被剪裁为元素的大小，但它们可以缩放 (使用 round) 或者均匀地分布 (使用 space).`

```
/* 单值语法 */
background-repeat: repeat-x;
background-repeat: repeat-y;
background-repeat: repeat;
background-repeat: space;
background-repeat: round;
background-repeat: no-repeat;

/* 双值语法: 水平horizontal | 垂直vertical */
background-repeat: repeat space;
background-repeat: repeat repeat;
background-repeat: round space;
background-repeat: no-repeat round;

background-repeat: inherit;
```

> <repeat-style> 单值语法是完整的双值语法的简写:

|单值 |等价于双值|
|:------| :------ |
|repeat-x |repeat no-repeat|
|repeat-y |no-repeat repeat|
|repeat |repeat repeat|
|space |space space|
|round |round round|
|no-repeat |	no-repeat no-repeat 在双值语法中, 第一个值表示水平重复行为, 第二个值表示垂直重复行为. 下面是关于每一个值是怎么工作的具体说明|

```

repeat	
图像会按需重复来覆盖整个背景图片所在的区域. 最后一个图像会被裁剪, 如果它的大小不合适的话.

space	
图像会尽可能得重复, 但是不会裁剪. 第一个和最后一个图像会被固定在元素(element)的相应的边上, 同时空白会均匀地分布在图像之间. background-position属性会被忽视, 除非只有一个图像能被无裁剪地显示. 只在一种情况下裁剪会发生, 那就是图像太大了以至于没有足够的空间来完整显示一个图像.

round	
随着允许的空间在尺寸上的增长, 被重复的图像将会伸展(没有空隙), 直到有足够的空间来添加一个图像. 当下一个图像被添加后, 所有的当前的图像会被压缩来腾出空间. 例如, 一个图像原始大小是260px, 重复三次之后, 可能会被伸展到300px, 直到另一个图像被加进来. 这样他们就可能被压缩到225px.

译者注: 关键是浏览器怎么计算什么时候应该添加一个图像进来, 而不是继续伸展.

no-repeat	
图像不会被重复(因为背景图像所在的区域将可能没有完全被覆盖). 那个没有被重复的背景图像的位置是由background-position属性来决定.
```

>background-size 设置背景图片大小。图片可以保有其原有的尺寸，或者拉伸到新的尺寸，或者在保持其原有比例的同时缩放到元素的可用空间的尺寸。

```
/* 关键字 */
background-size: cover
background-size: contain

/* 一个值: 这个值指定图片的宽度，图片的高度隐式的为auto */
background-size: 50%
background-size: 3em
background-size: 12px
background-size: auto

/* 两个值 */
/* 第一个值指定图片的宽度，第二个值指定图片的高度 */
background-size: 50% auto
background-size: 3em 25%
background-size: auto 6px
background-size: auto auto

/* 逗号分隔的多个值：设置多重背景 */
background-size: auto, auto     /* 不同于background-size: auto auto */
background-size: 50%, 25%, 25%
background-size: 6px, auto, contain

/* 全局属性 */
background-size: inherit;
background-size: initial;
background-size: unset;
```

```
<length>
<length> 值，指定背景图片大小，不能为负值。
<percentage>
<percentage> 值，指定背景图片相对背景区（background positioning area）的百分比。背景区由background-origin设置，默认为盒模型的内容区与内边距，也可设置为只有内容区，或者还包括边框。如果attachment 为fixed，背景区为浏览器可视区（即视口），不包括滚动条。不能为负值。
auto
以背景图片的比例缩放背景图片。
cover
缩放背景图片以完全覆盖背景区，可能背景图片部分看不见。和 contain 值相反，cover 值尽可能大的缩放背景图像并保持图像的宽高比例（图像不会被压扁）。该背景图以它的全部宽或者高覆盖所在容器。当容器和背景图大小不同时，背景图的 左/右 或者 上/下 部分会被裁剪。
contain
缩放背景图片以完全装入背景区，可能背景区部分空白。contain 尽可能的缩放背景并保持图像的宽高比例（图像不会被压缩）。该背景图会填充所在的容器。当背景图和容器的大小的不同时，容器的空白区域（上/下或者左/右）会显示由 background-color 设置的背景颜色。
位图一定有固有尺寸与固有比例，矢量图可能两者都有，也可能只有一个。渐变视为只有固有尺寸或者只有固有比例的图片。

如果指定了 background-size 的两个值并且不是auto：
背景图片按指定大小渲染。
contain 或 cover:
保留固有比例，最大的包含或覆盖背景区。如果图像没有固有比例，则按背景区大小。
auto 或 auto auto:
图像如果有两个长度，则按这个尺寸。如果没有固有尺寸与固有比例，则按背景区的大小。如果没有固有尺寸但是有固有比例， 效果同 contain。如果有一个长度与比例，则由此长度与比例计算大小。如果有一个长度但是没有比例，则使用此长度与背景区相应的长度。
一个为 auto 另一个不是auto:
如果图像有固有比例，则指定的长度使用指定值，未指定的长度由指定值与固有比例计算。如果图像没有固有比例，则指定的长度使用指定值，未指定的长度使用图像相应的固有长度，若没有固有长度，则使用背景区相应的长度。
注意，对于没有固有尺寸或固有比例的矢量图不是所有的浏览器都支持。特别注意测试Firefox 7- 与Firefox 8+，以确定不同之处能否接受。
```