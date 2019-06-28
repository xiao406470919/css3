# CSS3新特性

## 1 前言

> 用 CSS3 做过一些小动画，很好用，特别是里面一些新特性，都是 CSS2 不可比拟的，这里参照W3C和菜鸟教程等整理一些出来，当做笔记，也当做教程，共勉！

> CSS3 相比 CSS 2 对边框、背景、渐变、文本效果、字体、转换效果、过渡、动画、图片、用户界面、盒模型、媒体查询等都有了很大的改进，新增了不少功能和属性

## 2 CSS3边框

> 用 CSS3，可以创建圆角边框，添加阴影框，并作为边界的形象而不使用设计程序

### 2.1 属性

- border-radius
- box-shadow
- border-image

### 2.2 兼容性

- IE9 支持 border-radius 和 box-shadow 属性
- IE 浏览器不支持 border-image 属性
- Firefox、Chrome 以及 Safari 支持所有新的边框属性
- 对于 border-image，Safari 5 以及更老的版本需要前缀 -webkit-
- Opera 支持 border-radius 和 box-shadow 属性，但是对于 border-image 需要前缀 -o-

### 2.3 CSS3 圆角边框

> CSS3中border-radius属性是用于创建圆角的

#### 2.3.1 语法

```
border-radius：n1, n2, n3, n4 
/* n1 - n4 分别代表左上角、右上角、右下角、左下角 ，值可为百分比或像素值*/
```

#### 2.3.2 例子

```
div {
    width: 100px;
    height: 100px;
    /* border-radius: 25px; */
    border-radius: 25%;
}
```

### 2.4 CSS3盒阴影

> CSS3中的box-shadow属性被用来添加阴影

#### 2.4.1 语法

```
box-shadow: 水平阴影的位置 垂直阴影的位置 模糊距离 阴影的大小 阴影的颜色 阴影开始方向（默认是从里往外，设置inset就是从外往里）
```

#### 2.4.2 例子

```
div 
{ 
    width: 100px;
    height: 100px;
    background-color: yellow;
    box-shadow: 10px 10px 5px #888888 inset; 
}
```

### 2.5 CSS3边界图片

> border-image 属性允许你指定一个图片作为边框！用于创建上文边框的原始图像

#### 2.5.1 语法

```
border-image: 图片url 图像边界向内偏移 图像边界的宽度(默认为边框的宽度) 用于指定在边框外部绘制偏移的量（默认0） 铺满方式--重复（repeat）、拉伸（stretch）或铺满（round）（默认：拉伸（stretch））
```

#### 2.5.2 例子

```
div { 
    border-image:url(border.png) 30 30 round; 
    -webkit-border-image:url(border.png) 30 30 round; /* Safari 5 and older */ 
    -o-border-image:url(border.png) 30 30 round; /* Opera */ 
}
```

## 3 CSS3背景

> CSS3更新了几个新的背景属性，提供更大背景元素控制，通过这几个背景属性，您能够做出更加精美的样式

### 3.1 属性

- background-image
- background-size
- background-origin
- background-clip

### 3.2 兼容性

表格中的数字表示支持该属性的第一个浏览器版本号。

紧跟在 -webkit-, -ms- 或 -moz- 前的数字为支持该前缀属性的第一个浏览器版本号。

| 属性                                         | chrome           | IE   | Firefox       | Safari           | Opera         |
| -------------------------------------------- | ---------------- | ---- | ------------- | ---------------- | ------------- |
| background-image (with multiple backgrounds) | 4.0              | 9.0  | 3.6           | 3.1              | 11.5          |
| background-size                              | 4.0 1.0 -webkit- | 9.0  | 4.0 3.6 -moz- | 4.1 3.0 -webkit- | 10.5 10.0 -o- |
| background-origin                            | 1.0              | 9.0  | 4.0           | 3.0              | 10.5          |
| background-clip                              | 4.0              | 9.0  | 4.0           | 3.0              | 10.5          |

### 3.3 CSS3 背景图片

> CSS3中可以通过background-image属性添加背景图片

#### 3.3.1 语法

```
background-image: url, 定位, 平铺
```

#### 3.3.2 例子

> 不同的背景图像和图像用逗号隔开，所有的图片中显示在最顶端的为第一张

```
#example1 { 
    background-image: url(img_flwr.gif), url(paper.gif); 
    background-position: right bottom, left top; 
    background-repeat: no-repeat, repeat; 
}
```

> 可以给不同的图片设置多个不同的属性，每张图片之间依然用逗号隔开

```
#example1 {
    background: url(img_flwr.gif) right bottom no-repeat, url(paper.gif) left top repeat;
}
```

### 3.4 CSS3 背景图像大小

> background-size指定背景图像的大小。CSS3以前，背景图像大小由图像的实际大小决定

#### 3.4.1 语法

```
background-size: 宽 高; // 宽高可以是像素值，也可以是百分比
```

#### 3.4.2 例子

> 像素值

```
div
{
    background: url(img_flwr.gif);
    background-size: 80px 60px;
    background-repeat: no-repeat;
}
```

> 相对于父元素的宽度和高度的百分比的大小

```
div
{
    background: url(img_flwr.gif);
    background-size: 100% 100%;
    background-repeat: no-repeat;
}
```

### 3.5 CSS3 背景起始位置

> background-Origin属性指定了背景图像的位置区域

#### 3.5.1 语法

> content-box, padding-box,和 border-box区域内可以放置背景图像。

```
background-Origin: content-box, padding-box,和 border-box;
// 三个属性三选一，区域内可以放置背景图像
```

#### 3.5.2 例子

> 在 content-box 中定位背景图片

```
div 
{ 
    background: url(img_flwr.gif); 
    background-repeat: no-repeat; 
    background-size: 100% 100%; 
    background-origin: content-box; 
}
```

### 3.6 CSS3 背景图像裁剪

> CSS3中background-clip背景剪裁属性是从指定位置开始绘制

#### 3.6.1 语法

> 从content-box, padding-box,或 border-box位置进行背景图像裁剪

```
background-clip: content-box, padding-box,和 border-box;
// 三个属性三选一，区域内可以放置背景图像
```

#### 3.6.2 例子

> 从 content-box 开始裁剪

```
#example1 { 
    border: 10px dotted black; 
    padding: 35px; 
    background: yellow; 
    background-clip: content-box; 
}
```

## 4 CSS3渐变

> CSS3 渐变（gradients）可以让你在两个或多个指定的颜色之间显示平稳的过渡

### 4.1 属性

- **线性渐变（Linear Gradients）- 向下/向上/向左/向右/对角方向**
- **径向渐变（Radial Gradients）- 由它们的中心定义**

### 4.2 兼容性

> 表中的数字指定了完全支持该属性的第一个浏览器版本。
>
> 后边跟 -webkit-、-moz- 或 -o- 的数字指定了需加上前缀才能支持属性的第一个版本

| 属性                      | Chrome             | IE   | Firefox        | Safari           | Opera         |
| ------------------------- | ------------------ | ---- | -------------- | ---------------- | ------------- |
| linear-gradient           | 26.0 10.0 -webkit- | 10.0 | 16.0 3.6 -moz- | 6.1 5.1 -webkit- | 12.1 11.1 -o- |
| radial-gradient           | 26.0 10.0 -webkit- | 10.0 | 16.0 3.6 -moz- | 6.1 5.1 -webkit- | 12.1 11.6 -o- |
| repeating-linear-gradient | 26.0 10.0 -webkit- | 10.0 | 16.0 3.6 -moz- | 6.1 5.1 -webkit- | 12.1 11.1 -o- |
| repeating-radial-gradient | 26.0 10.0 -webkit- | 10.0 | 16.0 3.6 -moz- | 6.1 5.1 -webkit- | 12.1 11.6 -o- |

### 4.3 CSS3线性渐变

> 为了创建一个线性渐变，你必须至少定义两种颜色结点。颜色结点即你想要呈现平稳过渡的颜色。同时，你也可以设置一个起点和一个方向（或一个角度）

#### 4.3.1 语法

> **linear-gradient**

```
background: linear-gradient(direction, color-stop1, color-stop2, ...); 
```

#### 4.3.2 例子

> **从上到下：**从顶部开始的线性渐变。起点是红色，慢慢过渡到蓝色

```
#grad { 
  background: -webkit-linear-gradient(red, blue); /* Safari 5.1 - 6.0 */ 
  background: -o-linear-gradient(red, blue); /* Opera 11.1 - 12.0 */ 
  background: -moz-linear-gradient(red, blue); /* Firefox 3.6 - 15 */ 
  background: linear-gradient(red, blue); /* 标准的语法 */ 
}
```

> **从左到右：**从左边开始的线性渐变。起点是红色，慢慢过渡到蓝色

```
#grad { 
  background: -webkit-linear-gradient(left, red , blue); /* Safari 5.1 - 6.0 */ 
  background: -o-linear-gradient(right, red, blue); /* Opera 11.1 - 12.0 */ 
  background: -moz-linear-gradient(right, red, blue); /* Firefox 3.6 - 15 */ 
  background: linear-gradient(to right, red , blue); /* 标准的语法 */ 
}
```

> **对角：**从左上角开始（到右下角）的线性渐变。起点是红色，慢慢过渡到蓝色

```
#grad { 
  background: -webkit-linear-gradient(left top, red , blue); /* Safari 5.1 - 6.0 */ 
  background: -o-linear-gradient(bottom right, red, blue); /* Opera 11.1 - 12.0 */ 
  background: -moz-linear-gradient(bottom right, red, blue); /* Firefox 3.6 - 15 */ 
  background: linear-gradient(to bottom right, red , blue); /* 标准的语法 */ 
}
```

> 使用多个颜色节点从上到下的线性渐变

```
#grad { 
  background: -webkit-linear-gradient(red, green, blue); /* Safari 5.1 - 6.0 */ 
  background: -o-linear-gradient(red, green, blue); /* Opera 11.1 - 12.0 */ 
  background: -moz-linear-gradient(red, green, blue); /* Firefox 3.6 - 15 */ 
  background: linear-gradient(red, green, blue); /* 标准的语法 */ 
}
```

> 带有彩虹颜色和文本从左到右的线性渐变

```
#grad { 
  /* Safari 5.1 - 6.0 */ 
  background: -webkit-linear-gradient(left,red,orange,yellow,green,blue,indigo,violet); 
 /* Opera 11.1 - 12.0 */ 
  background: -o-linear-gradient(left,red,orange,yellow,green,blue,indigo,violet); 
  /* Firefox 3.6 - 15 */ 
  background: -moz-linear-gradient(left,red,orange,yellow,green,blue,indigo,violet); 
 /* 标准的语法 */ 
  background: linear-gradient(to right, red,orange,yellow,green,blue,indigo,violet); 
}
```

> **使用透明度（Transparency）**
>
> CSS3 渐变也支持透明度（transparency），可用于创建减弱变淡的效果。
>
> 为了添加透明度，我们使用 rgba() 函数来定义颜色结点。rgba() 函数中的最后一个参数可以是从 0 到 1 的值，它定义了颜色的透明度：0 表示完全透明，1 表示完全不透明
>
> 从左边开始的线性渐变。起点是完全透明，慢慢过渡到完全不透明的红色

```
#grad { 
  background: -webkit-linear-gradient(left,rgba(255,0,0,0),rgba(255,0,0,1)); /* Safari 5.1 - 6 */ 
  background: -o-linear-gradient(right,rgba(255,0,0,0),rgba(255,0,0,1)); /* Opera 11.1 - 12*/ 
  background: -moz-linear-gradient(right,rgba(255,0,0,0),rgba(255,0,0,1)); /* Firefox 3.6 - 15*/ 
  background: linear-gradient(to right, rgba(255,0,0,0), rgba(255,0,0,1)); /* 标准的语法 */ 
}
```

> **repeating-linear-gradient() 函数用于重复线性渐变**

```
#grad { 
  /* Safari 5.1 - 6.0 */ 
  background: -webkit-repeating-linear-gradient(red, yellow 10%, green 20%); 
  /* Opera 11.1 - 12.0 */ 
  background: -o-repeating-linear-gradient(red, yellow 10%, green 20%); 
  /* Firefox 3.6 - 15 */ 
  background: -moz-repeating-linear-gradient(red, yellow 10%, green 20%); 
  /* 标准的语法 */ 
  background: repeating-linear-gradient(red, yellow 10%, green 20%); 
}
```

#### 4.3.3 角度渐变

> **角度渐变：**属于线性渐变，如果你想要在渐变的方向上做更多的控制，你可以定义一个角度，而不用预定义方向（to bottom、to top、to right、to left、to bottom right，等等）

##### 4.3.3.1 语法

> 角度是指水平线和渐变线之间的角度，逆时针方向计算。换句话说，0deg 将创建一个从下到上的渐变，90deg 将创建一个从左到右的渐变

```
background: linear-gradient(angle, color-stop1, color-stop2);
```

**注意：**很多浏览器(Chrome,Safari,fiefox等)的使用了旧的标准，即 0deg 将创建一个从下到上的渐变，90deg 将创建一个从左到右的渐变。换算公式 **90 - x = y** 其中 x 为标准角度，y为非标准角度

##### 4.3.3.2 例子

> 带有指定的角度的线性渐变

```
#grad { 
  background: -webkit-linear-gradient(180deg, red, blue); /* Safari 5.1 - 6.0 */ 
  background: -o-linear-gradient(180deg, red, blue); /* Opera 11.1 - 12.0 */ 
  background: -moz-linear-gradient(180deg, red, blue); /* Firefox 3.6 - 15 */ 
  background: linear-gradient(180deg, red, blue); /* 标准的语法 */ 
}
```

### 4.4 CSS3径向渐变

> 说明：我这里是参照 W3C 总结的，发现了几篇更为详细的文档，这里推荐一下：
>
> - [CSS3 Gradient](http://www.w3cplus.com/content/css3-gradient)
> - [再说CSS3渐变——线性渐变](http://www.w3cplus.com/css3/new-css3-linear-gradient.html)
> - [再说CSS3渐变——径向渐变](http://www.w3cplus.com/css3/new-css3-radial-gradient.html)
> - [神奇的 conic-gradient 圆锥渐变](http://www.cnblogs.com/coco1s/p/7079529.html)

> 为了创建一个径向渐变，你也必须至少定义两种颜色结点。颜色结点即你想要呈现平稳过渡的颜色

#### 4.4.1 语法

> **radial-gradient**

> 可以指定渐变的中心、形状（圆形或椭圆形）、大小。默认情况下，渐变的中心是 center（表示在中心点），渐变的形状是 ellipse（表示椭圆形），渐变的大小是 farthest-corner（表示到最远的角落）

```
background: radial-gradient(center, shape size, start-color, ..., last-color)
// 渐变的中心、形状（圆形或椭圆形）、大小
```

#### 4.4.2 例子

> 颜色结点均匀分布的径向渐变

```
#grad { 
  background: -webkit-radial-gradient(red, green, blue); /* Safari 5.1 - 6.0 */ 
  background: -o-radial-gradient(red, green, blue); /* Opera 11.6 - 12.0 */ 
  background: -moz-radial-gradient(red, green, blue); /* Firefox 3.6 - 15 */ 
  background: radial-gradient(red, green, blue); /* 标准的语法 */ 
}
```

> 颜色结点不均匀分布的径向渐变

```
#grad { 
  background: -webkit-radial-gradient(red 5%, green 15%, blue 60%); /* Safari 5.1 - 6.0 */ 
  background: -o-radial-gradient(red 5%, green 15%, blue 60%); /* Opera 11.6 - 12.0 */ 
  background: -moz-radial-gradient(red 5%, green 15%, blue 60%); /* Firefox 3.6 - 15 */ 
  background: radial-gradient(red 5%, green 15%, blue 60%); /* 标准的语法 */ 
}
```

#### 4.4.3 设置形状

> shape 参数定义了形状。它可以是值 circle 或 ellipse。其中，circle 表示圆形，ellipse 表示椭圆形。默认值是 ellipse

> 形状为圆形的径向渐变

```
#grad { 
  background: -webkit-radial-gradient(circle, red, yellow, green); /* Safari 5.1 - 6.0 */ 
  background: -o-radial-gradient(circle, red, yellow, green); /* Opera 11.6 - 12.0 */ 
  background: -moz-radial-gradient(circle, red, yellow, green); /* Firefox 3.6 - 15 */ 
  background: radial-gradient(circle, red, yellow, green); /* 标准的语法 */ 
}
```

#### 4.4.4 不同尺寸大小关键字的使用

> size 参数定义了渐变的大小。它可以是以下四个值:
>
> - **closest-side**
> - **farthest-side**
> - **closest-corner**
> - **farthest-corner**

> 不同尺寸大小关键字的径向渐变

```
#grad1 { 
  /* Safari 5.1 - 6.0 */ 
  background: -webkit-radial-gradient(60% 55%, closest-side,blue,green,yellow,black); 
  /* Opera 11.6 - 12.0 */ 
 background: -o-radial-gradient(60% 55%, closest-side,blue,green,yellow,black); 
 /* Firefox 3.6 - 15 */ 
  background: -moz-radial-gradient(60% 55%, closest-side,blue,green,yellow,black); 
  /* 标准的语法 */ 
 background: radial-gradient(60% 55%, closest-side,blue,green,yellow,black); 
} 

#grad2 { 
 /* Safari 5.1 - 6.0 */ 
  background: -webkit-radial-gradient(60% 55%, farthest-side,blue,green,yellow,black); 
 /* Opera 11.6 - 12.0 */ 
  background: -o-radial-gradient(60% 55%, farthest-side,blue,green,yellow,black); 
  /* Firefox 3.6 - 15 */ 
 background: -moz-radial-gradient(60% 55%, farthest-side,blue,green,yellow,black); 
 /* 标准的语法 */ 
  background: radial-gradient(60% 55%, farthest-side,blue,green,yellow,black); 
}
```

#### 4.4.5 重复的径向渐变

> repeating-radial-gradient() 函数用于重复径向渐变

```
#grad { 
  /* Safari 5.1 - 6.0 */ 
  background: -webkit-repeating-radial-gradient(red, yellow 10%, green 15%); 
  /* Opera 11.6 - 12.0 */ 
  background: -o-repeating-radial-gradient(red, yellow 10%, green 15%); 
  /* Firefox 3.6 - 15 */ 
  background: -moz-repeating-radial-gradient(red, yellow 10%, green 15%); 
  /* 标准的语法 */ 
  background: repeating-radial-gradient(red, yellow 10%, green 15%); 
}
```

## 5 CSS3文本效果

> CSS3中包含几个新的文本特征

### 5.1 属性

- text-shadow
- box-shadow
- text-overflow
- word-wrap
- word-break

### 5.2 兼容性

> 浏览器支持

| 属性          | Chrome            | IE   | Firefox       | Safari           | Opera        |
| ------------- | ----------------- | ---- | ------------- | ---------------- | ------------ |
| text-shadow   | 4.0               | 10.0 | 3.5           | 4.0              | 9.5          |
| box-shadow    | 10.0 4.0 -webkit- | 9.0  | 4.0 3.5 -moz- | 5.1 3.1 -webkit- | 10.5         |
| text-overflow | 4.0               | 6.0  | 7.0           | 3.1              | 11.0 9.0 -o- |
| word-wrap     | 23.0              | 5.5  | 3.5           | 6.1              | 12.1         |
| word-break    | 4.0               | 5.5  | 15.0          | 3.1              | 15.0         |

### 5.3 CSS3文本阴影

> CSS3中，**text-shadow** 属性适用于文本阴影

#### 5.3.1 语法

```
text-shadow: 水平阴影，垂直阴影，模糊的距离，阴影的颜色
```

#### 5.3.2 例子

> 给标题添加阴影

```
h1{
    text-shadow: 5px 5px 5px #FF0000;
}
```

### 5.3.3 CSS3盒子阴影

> CSS3 中 **box-shadow** 属性适用于盒子阴影

#### 5.3.4 语法

```
box-shadow: x轴偏移 y轴偏移 模糊距离 阴影颜色
```

#### 5.3.5 例子

```
div { box-shadow: 10px 10px 5px yellow;}
```

> 也可以在 ::before 和 ::after 两个伪元素中添加阴影效果

```
#boxshadow { 
    position: relative; 
    box-shadow: 1px 2px 4px rgba(0, 0, 0, .5); 
    padding: 10px; bac kground: white;
} 
#boxshadow img { 
    width: 100%; 
    border: 1px solid #8a4419; 
    border-style: inset;
} 
#boxshadow::after { 
    content: ''; 
    position: absolute; 
    z-index: -1; /* hide shadow behind image */ 
    box-shadow: 0 15px 20px rgba(0, 0, 0, 0.3); 
    width: 70%; 
    left: 15%; /* one half of the remaining 30% */ 
    height: 100px; 
    bottom: 0;
}
```

> 文字卡片效果

```
div.card { 
    width: 250px; 
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19); 
    text-align: center;
}
```

### 5.4 CSS3溢出内容效果

> CSS3文本溢出属性**Text Overflow**指定应向用户如何显示溢出内容

#### 5.4.1 语法

> **clip：** 修剪文本
>
> **ellipsis：**显示省略符号来代表被修剪的文本
>
> **string：**使用给定的字符串来代表被修剪的文本

```
text-overflow: clip|ellipsis|string;
```

#### 5.4.2 例子

> [带有 hover 效果的 Text-overflow](http://www.w3school.com.cn/tiy/t.asp?f=css3_text-overflow_hover)

```
<!DOCTYPE html>
<html>
<head>
<style> 
div.test
{
white-space:nowrap; 
width:12em; 
overflow:hidden; 
border:1px solid #000000;
}

div.test:hover
{
text-overflow:inherit;
overflow:visible;
}
</style>

</head>

<body>

<p>如果您把光标移动到下面两个 div 上，就能够看到全部文本。</p>

<p>这个 div 使用 "text-overflow:ellipsis" ：</p>

<div class="test" style="text-overflow:ellipsis;">This is some long text that will not fit in the box</div>

<p>这个 div 使用 "text-overflow:clip"：</p>

<div class="test" style="text-overflow:clip;">This is some long text that will not fit in the box</div>

</body>
</html>
```

### 5.5 CSS3换行

> **word-wrap**自动换行属性允许您强制文本换行 - 即使这意味着分裂它中间的一个字

#### 5.5.1 语法

> **normal：**只在允许的断字点换行（浏览器保持默认处理）
>
> **break-word：**在长单词或 URL 地址内部进行换行

```
word-wrap: normal|break-word;
```

#### 5.5.2 例子

> 允许长文本换行

```
p {word-wrap: break-word;}
```

### 5.6 CSS3单词拆分行

> CSS3 单词拆分换行属性**word-break**指定换行规则

#### 5.6.1 语法

> **normal：**使用浏览器默认的换行规则
>
> **break-all：**允许在单词内换行
>
> **keep-all：**只能在半角空格或连字符处换行

```
word-break: normal|break-all|keep-all;
```

#### 5.6.2 例子

```
p.test1 { 
    word-break: keep-all;
} 
p.test2 { 
    word-break: break-all;
}
```

### 5.7 CSS其他文本属性

> 内容来自菜鸟教程

| 属性                                                         | 描述                                                    | CSS  |
| ------------------------------------------------------------ | ------------------------------------------------------- | ---- |
| [hanging-punctuation](http://www.runoob.com/cssref/css3-pr-hanging-punctuation.html) | 规定标点字符是否位于线框之外。                          | 3    |
| [punctuation-trim](http://www.runoob.com/cssref/css3-pr-punctuation-trim.html) | 规定是否对标点字符进行修剪。                            | 3    |
| [text-align-last](http://www.runoob.com/cssref/css3-pr-text-align-last.html) | 设置如何对齐最后一行或紧挨着强制换行符之前的行。        | 3    |
| [text-emphasis](http://www.runoob.com/css3/css3-pr-text-emphasis.html) | 向元素的文本应用重点标记以及重点标记的前景色。          | 3    |
| [text-justify](http://www.runoob.com/cssref/css3-pr-text-justify.html) | 规定当 text-align 设置为 "justify" 时所使用的对齐方法。 | 3    |
| [text-outline](http://www.runoob.com/cssref/css3-pr-text-outline.html) | 规定文本的轮廓。                                        | 3    |
| [text-overflow](http://www.runoob.com/cssref/css3-pr-text-overflow.html) | 规定当文本溢出包含元素时发生的事情。                    | 3    |
| [text-shadow](http://www.runoob.com/cssref/css3-pr-text-shadow.html) | 向文本添加阴影。                                        | 3    |
| [text-wrap](http://www.runoob.com/cssref/css3-pr-text-wrap.html) | 规定文本的换行规则。                                    | 3    |
| [word-break](http://www.runoob.com/cssref/css3-pr-word-break.html) | 规定非中日韩文本的换行规则。                            | 3    |
| [word-wrap](http://www.runoob.com/cssref/css3-pr-word-wrap.html) | 允许对长的不可分割的单词进行分割并换行到下一行。        | 3    |

## 6 CSS3字体

> 通过CSS3，web设计师可以使用他们喜欢的任意字体

### 6.1 属性

> 当您找到或购买到希望使用的字体时，可将该字体文件存放到web服务器上，它会在需要时被自动下载到用户的计算机上

- **@font-face**

### 6.2 兼容性

> 表格中的数字表示支持该属性的第一个浏览器版本号。

| 属性       | Chrome | IE   | Firefox | Safari | Opera |
| ---------- | ------ | ---- | ------- | ------ | ----- |
| @font-face | 4.0    | 9.0  | 3.5     | 3.2    | 10.0  |

> - Internet Explorer 9+, Firefox, Chrome, Safari, 和 Opera 支持 WOFF (Web Open Font Format) 字体.
> - Firefox, Chrome, Safari, 和 Opera 支持 .ttf(True Type字体)和.otf(OpenType)字体字体类型）。
> - Chrome, Safari 和 Opera 也支持 SVG 字体/折叠.
> - Internet Explorer 同样支持 EOT (Embedded OpenType) 字体.
> - **需要注意的是：** Internet Explorer 8 以及更早的版本不支持新的 @font-face 规则。

### 6.3 CSS3设置字体

> CSS3中用**@font-face**属性来设置自己喜欢的字体

#### 6.3.1 语法

> 在新的 @font-face 规则中，您必须首先定义字体的名称（比如 myFirstFont），然后指向该字体文件

#### 6.3.2 例子

```
@font-face
{
   font-family: myFirstFont;
   src: url(sansation_light.woff);
}

div
{
   font-family:myFirstFont;
}
```

### 6.3.3 CSS3 字体描述

> 下表列出了所有的字体描述和里面的@font-face规则定义
>
> 说明：表格来源于 W3C

| 描述符        | 值                                                           | 描述                                                         |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| font-family   | *name*                                                       | 必需。规定字体的名称。                                       |
| src           | *URL*                                                        | 必需。定义字体文件的 URL。                                   |
| font-stretch  | normal/condensed/ultra-condensed/extra-condensed/semi-condensed/expanded/semi-expanded/extra-expanded/ultra-expanded | 可选。定义如何拉伸字体。默认是 "normal"。                    |
| font-style    | normalitalicoblique                                          | 可选。定义字体的样式。默认是 "normal"。                      |
| font-weight   | normal/bold/100-900                                          | 可选。定义字体的粗细。默认是 "normal"。                      |
| unicode-range | *unicode-range*                                              | 可选。定义字体支持的 UNICODE 字符范围。默认是 "U+0-10FFFF"。 |

## 7 CSS3 2D 转换

> 可以移动，比例化，反过来，旋转，和拉伸元素

### 7.1 属性

- transform
- transform-origin

### 7.2 方法

- translate()
- rotate()
- scale()
- skew()
- matrix()

### 7.3 兼容性

> 表格中的数字表示支持该属性的第一个浏览器版本号
>
> 紧跟在 -webkit-, -ms- 或 -moz- 前的数字为支持该前缀属性的第一个浏览器版本号

| 属性                                | Chrome            | IE            | Firefox        | Safari       | Opera                            |
| ----------------------------------- | ----------------- | ------------- | -------------- | ------------ | -------------------------------- |
| transform                           | 36.0 4.0 -webkit- | 10.0 9.0 -ms- | 16.0 3.5 -moz- | 3.2 -webkit- | 23.0 15.0 -webkit- 12.1 10.5 -o- |
| transform-origin (two-value syntax) | 36.0 4.0 -webkit- | 10.0 9.0 -ms- | 16.0 3.5 -moz- | 3.2 -webkit- | 23.0 15.0 -webkit- 12.1 10.5 -o- |

> Internet Explorer 10, Firefox, 和 Opera支持transform 属性.
>
> Chrome 和 Safari 要求前缀 -webkit- 版本.
>
> **注意：** Internet Explorer 9 要求前缀 -ms- 版本.

### 7.4 translate()

> 移动

> translate()方法，根据左(X轴)和顶部(Y轴)位置给定的参数，从当前元素位置移动

#### 7.4.1 语法

```
transform: translate(x轴移动距离, y轴移动距离) // 原点在左上角
```

#### 7.4.2 案例

> translate值（50px，100px）是从左边元素移动50个像素，并从顶部移动100像素

```
div { 
    transform: translate(50px,100px); 
    -ms-transform: translate(50px,100px); /* IE 9 */ 
    -webkit-transform: translate(50px,100px); /* Safari and Chrome */ 
}
```

### 7.5 rotate()

> 旋转，**旋转过后，原点会跟着变化**

> rotate()方法，在一个给定度数顺时针旋转的元素。负值是允许的，这样是元素逆时针旋转

#### 7.5.1 语法

```
transform: rotate(angle) // 括号内填写旋转角度
```

#### 7.5.2 例子

> rotate值（30deg）元素顺时针旋转30度

```
div { 
    transform: rotate(30deg); 
    -ms-transform: rotate(30deg); /* IE 9 */ 
    -webkit-transform: rotate(30deg); /* Safari and Chrome */ 
}  
```

### 7.6 scale()

> 缩放

> scale()方法，该元素增加或减少的大小，取决于宽度（X轴）和高度（Y轴）的参数

#### 7.6.1 语法

```
transform: scale(宽度的倍数, 高度的倍数)
```

#### 7.6.2 例子

> scale（2,4）转变宽度为原来的大小的2倍，和其原始大小4倍的高度

```
div 
{ 
    transform: scale(2,4); 
    -ms-transform: scale(2,4); /* IE 9 */ 
    -webkit-transform: scale(2,4); /* Safari and Chrome */ 
}  
```

### 7.7 skew()

> CSS3 倾斜

> 包含两个参数值，分别表示X轴和Y轴倾斜的角度，如果第二个参数为空，则默认为0，参数为负表示向相反方向倾斜

#### 7.7.1 语法

> - skewX( );表示只在X轴(水平方向)倾斜。
> - skewY( );表示只在Y轴(垂直方向)倾斜。

```
transform: skew(相对于x轴角度, 相对于y轴角度)
```

#### 7.7.2 例子

> skew(30deg,20deg) 是元素在X轴和Y轴上倾斜30度20度
>
> 此处 W3C 上教程有误，他写的是 `skew(30deg,20deg) 是元素在X轴和Y轴上倾斜20度30度`

```
div { 
    transform: skew(30deg,20deg); 
    -ms-transform: skew(30deg,20deg); /* IE 9 */ 
    -webkit-transform: skew(30deg,20deg); /* Safari and Chrome */ 
}  
```

### 7.8 matrix()

> **CSS3 矩阵**，反正我用得少

> **matrix()方法将2D变换方法合并成一个**

#### 7.8.1 语法

```
transform: matrix(旋转角度, 缩放比例, 移动, 倾斜)
```

#### 7.8.2 例子

> 利用matrix()方法旋转div元素30°

```
div 
{ 
    transform:matrix(0.866,0.5,-0.5,0.866,0,0); 
    -ms-transform:matrix(0.866,0.5,-0.5,0.866,0,0); /* IE 9 */ 
    -webkit-transform:matrix(0.866,0.5,-0.5,0.866,0,0); /* Safari and Chrome */ 
} 
```

## 8 CSS3 3D转换

> CSS3 允许您使用 3D 转换来对元素进行格式化

### 8.1 兼容性

> 表格中的数字表示支持该属性的第一个浏览器版本号
>
> 紧跟在 -webkit-, -ms- 或 -moz- 前的数字为支持该前缀属性的第一个浏览器版本号

| 属性                                  | Chrome             | IE   | Firefox         | Safari       | Opera              |
| ------------------------------------- | ------------------ | ---- | --------------- | ------------ | ------------------ |
| transform                             | 36.0 12.0 -webkit- | 10.0 | 16.0 10.0 -moz- | 4.0 -webkit- | 23.0 15.0 -webkit- |
| transform-origin (three-value syntax) | 36.0 12.0 -webkit- | 10.0 | 16.0 10.0 -moz- | 4.0 -webkit- | 23.0 15.0 -webkit- |
| transform-style                       | 36.0 12.0 -webkit- | 11.0 | 16.0 10.0 -moz- | 4.0 -webkit- | 23.0 15.0 -webkit- |
| perspective                           | 36.0 12.0 -webkit- | 10.0 | 16.0 10.0 -moz- | 4.0 -webkit- | 23.0 15.0 -webkit- |
| perspective-origin                    | 36.0 12.0 -webkit- | 10.0 | 16.0 10.0 -moz- | 4.0 -webkit- | 23.0 15.0 -webkit- |
| backface-visibility                   | 36.0 12.0 -webkit- | 10.0 | 16.0 10.0 -moz- | 4.0 -webkit- | 23.0 15.0 -webkit- |

### 8.2 rotateX()

#### 8.2.1 例子

> rotateX()方法，围绕其在一个给定度数X轴旋转的元素

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>W3C(w3cschool.cn)</title> 
<style> 
div
{
    width:100px;
    height:75px;
    background-color:red;
    border:1px solid black;
}
div#div2
{
    transform:rotateX(120deg);
    -webkit-transform:rotateX(120deg); /* Safari and Chrome */
}
</style>
</head>
<body>
<p><b>注意:</b> Internet Explorer 9 (以及更早版本的浏览器) 和 Opera 不支持 rotateX 方法.</p>
<div>Hello. This is a DIV element.</div>
<div id="div2">Hello. This is a DIV element.</div>
</body>
</html>
```

### 8.3 rotateY()

#### 8.3.1 例子

> rotateY()方法，围绕其在一个给定度数Y轴旋转的元素

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>W3C(w3cschool.cn)</title> 
<style> 
div
{
    width:100px;
    height:75px;
    background-color:red;
    border:1px solid black;
}
div#div2
{
    transform:rotateY(130deg);
    -webkit-transform:rotateY(130deg); /* Safari and Chrome */
}
</style>
</head>
<body>
<p><b>注意:</b> Internet Explorer 9 (以及更早版本的浏览器) 和 Opera 不支持 rotateY方法.</p>
<div>Hello. This is a DIV element.</div>
<div id="div2">Hello. This is a DIV element.</div>
</body>
</html>
```

### 8.4 CSS3 转换属性

> 下表列出了CSS3所有的转换属性

| 属性                                                         | 描述                                 | **CSS** |
| ------------------------------------------------------------ | ------------------------------------ | ------- |
| [transform](https://www.w3cschool.cn/cssref/css3-pr-transform.html) | 向元素应用 2D 或 3D 转换。           | 3       |
| [transform-origin](https://www.w3cschool.cn/cssref/css3-pr-transform-origin.html) | 允许你改变被转换元素的位置。         | 3       |
| [transform-style](https://www.w3cschool.cn/cssref/css3-pr-transform-style.html) | 规定被嵌套元素如何在 3D 空间中显示。 | 3       |
| [perspective](https://www.w3cschool.cn/cssref/css3-pr-perspective.html) | 规定 3D 元素的透视效果。             | 3       |
| [perspective-origin](https://www.w3cschool.cn/cssref/css3-pr-perspective-origin.html) | 规定 3D 元素的底部位置。             | 3       |
| [backface-visibility](https://www.w3cschool.cn/cssref/css3-pr-backface-visibility.html) | 定义元素在不面对屏幕时是否可见。     | 3       |

### 8.5 CSS3 3D 转换方法

> 类似于 CSS3 2D 转换方法的使用

| 函数                                                         | 描述                                          |
| ------------------------------------------------------------ | --------------------------------------------- |
| matrix3d(*n***,***n***,** *n***,***n***,***n***,***n* **,***n***,***n***,***n* **,***n***,***n***,***n***,***n***,***n***,***n***,***n* ) | 定义 3D 转换**，**使用 16 个值的 4x4 矩阵。   |
| translate3d(*x***,***y***,***z*)                             | 定义 3D 转化。                                |
| translateX(*x*)                                              | 定义 3D 转化**，**仅使用用于 X 轴的值。       |
| translateY(*y*)                                              | 定义 3D 转化**，**仅使用用于 Y 轴的值。       |
| translateZ(*z*)                                              | 定义 3D 转化**，**仅使用用于 Z 轴的值。       |
| scale3d(*x***,***y***,***z*)                                 | 定义 3D 缩放转换。                            |
| scaleX(*x*)                                                  | 定义 3D 缩放转换**，**通过给定一个 X 轴的值。 |
| scaleY(*y*)                                                  | 定义 3D 缩放转换**，**通过给定一个 Y 轴的值。 |
| scaleZ(*z*)                                                  | 定义 3D 缩放转换**，**通过给定一个 Z 轴的值。 |
| rotate3d(*x***,***y***,***z***,***angle*)                    | 定义 3D 旋转。                                |
| rotateX(*angle*)                                             | 定义沿 X 轴的 3D 旋转。                       |
| rotateY(*angle*)                                             | 定义沿 Y 轴的 3D 旋转。                       |
| rotateZ(*angle*)                                             | 定义沿 Z 轴的 3D 旋转。                       |
| perspective(*n*)                                             | 定义 3D 转换元素的透视视图。                  |

## 9 CSS3 过渡

> CSS3中，我们为了添加某种效果可以从一种样式转变到另一个的时候，无需使用Flash动画或JavaScript

### 9.1 属性

| 属性                                                         | 描述                                         | CSS  |
| ------------------------------------------------------------ | -------------------------------------------- | ---- |
| [transition](https://www.w3cschool.cn/cssref/css3-pr-transition.html) | 简写属性，用于在一个属性中设置四个过渡属性。 | 3    |
| [transition-property](https://www.w3cschool.cn/cssref/css3-pr-transition-property.html) | 规定应用过渡的 CSS 属性的名称。              | 3    |
| [transition-duration](https://www.w3cschool.cn/cssref/css3-pr-transition-duration.html) | 定义过渡效果花费的时间。默认是 0。           | 3    |
| [transition-timing-function](https://www.w3cschool.cn/cssref/css3-pr-transition-timing-function.html) | 规定过渡效果的时间曲线。默认是 "ease"。      | 3    |
| [transition-delay](https://www.w3cschool.cn/cssref/css3-pr-transition-delay.html) | 规定过渡效果何时开始。默认是 0。             | 3    |

### 9.2 兼容性

> 表格中的数字表示支持该属性的第一个浏览器版本号
>
> 紧跟在 -webkit-, -ms- 或 -moz- 前的数字为支持该前缀属性的第一个浏览器版本号

| 属性                       | Chrome            | IE   | Firefox        | Safari           | Opera         |
| -------------------------- | ----------------- | ---- | -------------- | ---------------- | ------------- |
| transition                 | 26.0 4.0 -webkit- | 10.0 | 16.0 4.0 -moz- | 6.1 3.1 -webkit- | 12.1 10.5 -o- |
| transition-delay           | 26.0 4.0 -webkit- | 10.0 | 16.0 4.0 -moz- | 6.1 3.1 -webkit- | 12.1 10.5 -o- |
| transition-duration        | 26.0 4.0 -webkit- | 10.0 | 16.0 4.0 -moz- | 6.1 3.1 -webkit- | 12.1 10.5 -o- |
| transition-property        | 26.0 4.0 -webkit- | 10.0 | 16.0 4.0 -moz- | 6.1 3.1 -webkit- | 12.1 10.5 -o- |
| transition-timing-function | 26.0 4.0 -webkit- | 10.0 | 16.0 4.0 -moz- | 6.1 3.1 -webkit- | 12.1 10.5 -o- |

### 9.3 transition

#### 9.3.1 语法

> transition需要配合一个变化的属性进行

```
div:hover {
    width: 300px;
}
div {
    transition: 指定需要变化的属性（例如width）,完成时间, 转速曲线, 延迟执行的时间 
}
```

#### 9.3.2 例子

> 指定当鼠标经过 div 的 1s 之后 , div 的 width 在 1 秒时间内，匀速变化为 300 px

```
div:hover {
    width: 300px;
}
div {
    transition: width 1s linear 1s;
}
```

> 拆分写法

```
div:hover {
    width: 300px;
}

div { 
    transition-property: width; 
    transition-duration: 1s; 
    transition-timing-function: linear; 
    transition-delay: 1s; 
    /* Safari */ 
    -webkit-transition-property: width; 
    -webkit-transition-duration: 1s; 
    -webkit-transition-timing-function: linear; 
    -webkit-transition-delay: 1s; 
}
```

**注：**这里看到了一篇很棒的文档，推荐一下[CSS3过渡和动画](https://segmentfault.com/a/1190000010780991#articleHeader1)

## 10 CSS3 动画

> CSS3，我们可以创建动画，它可以取代许多网页动画图像，Flash动画，和JAVAScripts

### 10.1 属性

- @keyframes
- animation

### 10.2 兼容性

> Internet Explorer 10、Firefox 以及 Opera 支持 @keyframes 规则和 animation 属性
>
> 紧跟在 -webkit-, -ms- 或 -moz- 前的数字为支持该前缀属性的第一个浏览器版本号

| 属性       | Chrome            | IE   | Firefox        | Safari           | Opera                       |
| ---------- | ----------------- | ---- | -------------- | ---------------- | --------------------------- |
| @keyframes | 43.0 4.0 -webkit- | 10.0 | 16.0 5.0 -moz- | 9.0 4.0 -webkit- | 30.0 15.0 -webkit- 12.0 -o- |
| animation  | 43.0 4.0 -webkit- | 10.0 | 16.0 5.0 -moz- | 9.0 4.0 -webkit- | 30.0 15.0 -webkit- 12.0 -o- |

### 10.3 语法

> @keyframes 和 animation 一般配合使用，使用 @keyframes 定义一个动画，使用 animation 去执行这个动画

### 10.4 例子

> 必须定义动画的名称和动画的持续时间。如果省略的持续时间，动画将无法运行，因为默认值是0

```
@keyframes myfirst
{
    from {background: red;}
    to {background: yellow;}
}

@-webkit-keyframes myfirst /* Safari and Chrome */
{
    from {background: red;}
    to {background: yellow;}
}

div {
    animation: myfirst 5s;
    -webkit-animation: myfirst 5s; /* Safari and Chrome */
}  
```

> 可以以百分比指定动画发生时间

> 为了得到最佳的浏览器支持，您应该始终定义 0% 和 100% 选择器

> 当动画为 25% 及 50% 时改变背景色，然后当动画 100% 完成时再次改变

```
@keyframes myfirst
{
    0%   {background: red;}
    25%  {background: yellow;}
    50%  {background: blue;}
    100% {background: green;}
}

@-webkit-keyframes myfirst /* Safari and Chrome */
{
    0%   {background: red;}
    25%  {background: yellow;}
    50%  {background: blue;}
    100% {background: green;}
}

div {
    animation: myfirst 5s;
    -webkit-animation: myfirst 5s; /* Safari and Chrome */
}  
```

> 改变背景色和位置

```
@keyframes myfirst
{
    0%   {background: red; left:0px; top:0px;}
    25%  {background: yellow; left:200px; top:0px;}
    50%  {background: blue; left:200px; top:200px;}
    75%  {background: green; left:0px; top:200px;}
    100% {background: red; left:0px; top:0px;}
}

@-webkit-keyframes myfirst /* Safari and Chrome */
{
    0%   {background: red; left:0px; top:0px;}
    25%  {background: yellow; left:200px; top:0px;}
    50%  {background: blue; left:200px; top:200px;}
    75%  {background: green; left:0px; top:200px;}
    100% {background: red; left:0px; top:0px;}
}

div {
    animation: myfirst 5s;
    -webkit-animation: myfirst 5s; /* Safari and Chrome */
}  
```

### 10.5 CSS3的动画属性

> 下面的表格列出了 @keyframes 规则和所有动画属性

| 属性                                                         | 描述                                                     | CSS  |
| ------------------------------------------------------------ | -------------------------------------------------------- | ---- |
| [@keyframes](https://www.w3cschool.cn/cssref/css3-pr-animation-keyframes.html) | 规定动画。                                               | 3    |
| [animation](https://www.w3cschool.cn/cssref/css3-pr-animation.html) | 所有动画属性的简写属性，除了 animation-play-state 属性。 | 3    |
| [animation-name](https://www.w3cschool.cn/cssref/css3-pr-animation-name.html) | 规定 @keyframes 动画的名称。                             | 3    |
| [animation-duration](https://www.w3cschool.cn/cssref/css3-pr-animation-duration.html) | 规定动画完成一个周期所花费的秒或毫秒。默认是 0。         | 3    |
| [animation-timing-function](https://www.w3cschool.cn/cssref/css3-pr-animation-timing-function.html) | 规定动画的速度曲线。默认是 "ease"。                      | 3    |
| [animation-delay](https://www.w3cschool.cn/cssref/css3-pr-animation-delay.html) | 规定动画何时开始。默认是 0。                             | 3    |
| [animation-iteration-count](https://www.w3cschool.cn/cssref/css3-pr-animation-iteration-count.html) | 规定动画被播放的次数。默认是 1。                         | 3    |
| [animation-direction](https://www.w3cschool.cn/cssref/css3-pr-animation-direction.html) | 规定动画是否在下一周期逆向地播放。默认是 "normal"。      | 3    |
| [animation-play-state](https://www.w3cschool.cn/cssref/css3-pr-animation-play-state.html) | 规定动画是否正在运行或暂停。默认是 "running"。           | 3    |

> 运行myfirst动画，设置所有的属性

```
div {
    animation-name: myfirst;
    animation-duration: 5s;
    animation-timing-function: linear;
    animation-delay: 2s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    animation-play-state: running;
/* Safari and Chrome: */
    -webkit-animation-name: myfirst;
    -webkit-animation-duration: 5s;
    -webkit-animation-timing-function: linear;
    -webkit-animation-delay: 2s;
    -webkit-animation-iteration-count: infinite;
    -webkit-animation-direction: alternate;
    -webkit-animation-play-state: running;
}
```

> 与上面的动画相同，但是使用了简写的动画 animation 属性

```
div {
    animation: myfirst 5s linear 2s infinite alternate;
    /* Safari and Chrome: */
    -webkit-animation: myfirst 5s linear 2s infinite alternate;
}
```

## 11 CSS3 弹性盒子(Flex Box)

**详见Flex布局**

## 12 CSS3用户界面

> 在 CSS3 中, 增加了一些新的用户界面特性来调整元素尺寸，框尺寸和外边框

### 12.1 属性

- resize
- box-sizing
- outline-offset

### 12.2 兼容性

> 表格中的数字表示支持该属性的第一个浏览器版本号
>
> 紧跟在 -webkit-, -ms- 或 -moz- 前的数字为支持该前缀属性的第一个浏览器版本号

| 属性           | Chrome            | IE     | Firefox        | Safari           | Opera |
| -------------- | ----------------- | ------ | -------------- | ---------------- | ----- |
| resize         | 4.0               | 不兼容 | 5.0 4.0 -moz-  | 4.0              | 15.0  |
| box-sizing     | 10.0 4.0 -webkit- | 8.0    | 29.0 2.0 -moz- | 5.1 3.1 -webkit- | 9.5   |
| outline-offset | 4.0               | 不兼容 | 5.0 4.0 -moz-  | 4.0              | 9.5   |

### 12.3 CSS3 调整尺寸

> CSS3中，resize属性指定一个元素是否应该由用户去调整大小

#### 12.3.1 语法

> resize属性指定一个元素是否是由用户调整大小的

```
resize: none|both|horizontal|vertical
```

| 值         | 描述                         |
| ---------- | ---------------------------- |
| none       | 用户无法调整元素的尺寸。     |
| both       | 用户可调整元素的高度和宽度。 |
| horizontal | 用户可调整元素的宽度。       |
| vertical   | 用户可调整元素的高度。       |

#### 12.3.2 例子

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>W3Cschool教程(w3cschool.cn)</title>
<style> 
div
{
    border:2px solid;
    padding:10px 40px; 
    width:300px;
    resize:both;
    overflow:auto;
}
</style>
</head>
<body>

<p><b>注意:</b> Firefox, Safari,和 Chrome 兼容 resize 属性.</p>

<div>The resize property specifies whether or not an element is resizable by the user.</div>

</body>
</html>
```

### 12.4 CSS3 方框大小调整

> box-sizing 属性允许您以确切的方式定义适应某个区域的具体内容
>
> 简单来说就是当需要考虑 width 或者 height 包不包括 padding 和 border 的时候可以考虑使用 box-sizing
>
> 例如：box-sizing:border-box的时候，边框和padding包含在元素的宽高之内

#### 12.4.1 语法

```
box-sizing: content-box|border-box|inherit
```

| 值          | 说明                                                         |
| ----------- | ------------------------------------------------------------ |
| content-box | 这是CSS2.1指定的宽度和高度的行为。指定元素的宽度和高度（最小/最大属性）适用于box的宽度和高度。元素的填充和边框布局和绘制指定宽度和高度除外 |
| border-box  | 指定宽度和高度（最小/最大属性）确定元素边框box。也就是说，对元素指定宽度和高度包括padding和border的指定。内容的宽度和高度减去各自双方该边框和填充的宽度从指定的"宽度"和"高度"属性计算 |
| inherit     | 指定box-sizing属性的值，应该从父元素继承                     |

#### 12.4.2 例子

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>W3Cschool教程(w3cschool.cn)</title>
<style> 
div.container
{
    width:30em;
    border:1em solid;
}
div.box
{
    box-sizing:border-box;
    -moz-box-sizing:border-box; /* Firefox */
    width:50%;
    border:1em solid red;
    float:left;
}
</style>
</head>
<body>

<div class="container">
<div class="box">This div occupies the left half.</div>
<div class="box">This div occupies the right half.</div>
</div>

</body>
</html>
```

### 12.5 CSS3 外形修饰

> 简单来说就是在边框 border 外面又加了一层 outline-offset
>
> 轮廓与边框有两点不同：
>
> - 轮廓不占用空间
> - 轮廓可能是非矩形

#### 12.5.1 语法

```
outline-offset: length|inherit
```

| 值       | 描述                                         |
| -------- | -------------------------------------------- |
| *length* | 轮廓与边框边缘的距离。                       |
| inherit  | 规定应从父元素继承 outline-offset 属性的值。 |

#### 12.5.2 例子

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>W3Cschool教程(w3cschool.cn)</title>
<style> 
div
{
    margin:20px;
    width:150px; 
    padding:10px;
    height:70px;
    border:2px solid black;
    outline:2px solid red;
    outline-offset:15px;
} 
</style>
</head>
<body>

<p><b>注意:</b> Internet Explorer 不兼容 outline-offset属性.</p>

<div>这个 div有一个轮廓边界15 px边境外的边缘。</div>

</body>
</html>
```

## 13 CSS3 媒体查询

> 媒体查询很多就是用来进行响应式开发了

### 13.1 兼容性

| 属性   | Chrome | IE   | Firefox | Safari | Opera |
| ------ | ------ | ---- | ------- | ------ | ----- |
| @media | 21.0   | 9.0  | 3.5     | 4.0    | 9.0   |

### 13.2 @media

#### 13.2.1 语法

```
@media 媒体类型 and (条件) {
    
}
```

#### 13.2.2 例子

**利用媒体查询做响应式布局开发：**

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title></title> 
<style>
body {
    background-color: pink;
}
@media screen and (max-width: 960px) {
    body {
        background-color: darkgoldenrod;
    }
}
@media screen and (max-width: 480px) {
    body {
        background-color: lightgreen;
    }
}
</style>
</head>
<body>

<h1>重置浏览器窗口查看效果！</h1>
<p>如果媒体类型屏幕的可视窗口宽度小于 960 px ，背景颜色将改变。</p>
<p>如果媒体类型屏幕的可视窗口宽度小于 480 px ，背景颜色将改变。</p>

</body>
</html>
```