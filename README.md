# display-flex
#display-flex兼容微信浏览器

这里还是假设flex容器为 .box ，子元素为 .item 。

<h3>定义容器的 display 属性</h3>
```css
.box{
display: -webkit-box; /* 老版本语法: Safari, iOS, Android browser, older WebKit browsers. */
display: -moz-box; /* 老版本语法: Firefox (buggy) */
display: -ms-flexbox; /* 混合版本语法: IE 10 */
display: -webkit-flex; /* 新版本语法: Chrome 21+ */
display: flex; /* 新版本语法: Opera 12.1, Firefox 22+ */
}
```

这里还要注意的是，如果子元素是行内元素，在很多情况下都要使用 display:block 或 display:inline-block 把行内子元素变成块元素

（例如使用 box-flex 属性），这也是旧版语法和新版语法的区别之一。

<h3>子元素主轴对齐方式</h3>
```css
.box{
-webkit-box-pack: center;
-moz-justify-content: center;
-webkit-justify-content: center;
justify-content: center;
}
```
这里旧版语法有4个参数，而新版语法有5个参数，兼容写法新版语法的 space-around 是不可用的：
```css
.box{
box-pack: start | end | center | justify;
/*主轴对齐：左对齐（默认） | 右对齐 | 居中对齐 | 左右对齐*/

justify-content: flex-start | flex-end | center | space-between | space-around;
/*主轴对齐方式：左对齐（默认） | 右对齐 | 居中对齐 | 两端对齐 | 平均分布*/
}
```
<h3>子元素交叉轴对齐方式</h3>
```css
.box{
-webkit-box-align: center;
-moz-align-items: center;
-webkit-align-items: center;
align-items: center;
}
```
```css
.box{
box-align: start | end | center | baseline | stretch;
/*交叉轴对齐：顶部对齐（默认） | 底部对齐 | 居中对齐 | 文本基线对齐 | 上下对齐并铺满*/

align-items: flex-start | flex-end | center | baseline | stretch;
/*交叉轴对齐方式：顶部对齐（默认） | 底部对齐 | 居中对齐 | 上下对齐并铺满 | 文本基线对齐*/
}
```
<h3>子元素的显示方向</h3>
左到右
```css
.box{
-webkit-box-direction: normal;
-webkit-box-orient: horizontal;
-moz-flex-direction: row;
-webkit-flex-direction: row;
flex-direction: row;
}
```
右到左
```css
.box{
-webkit-box-pack: end;
-webkit-box-direction: reverse;
-webkit-box-orient: horizontal;
-moz-flex-direction: row-reverse;
-webkit-flex-direction: row-reverse;
flex-direction: row-reverse;
}
```
上到下
```css
.box{
-webkit-box-direction: normal;
-webkit-box-orient: vertical;
-moz-flex-direction: column;
-webkit-flex-direction: column;
flex-direction: column;
}
```
下到上
```css
.box{
-webkit-box-pack: end;
-webkit-box-direction: reverse;
-webkit-box-orient: vertical;
-moz-flex-direction: column-reverse;
-webkit-flex-direction: column-reverse;
flex-direction: column-reverse;
}
```
<h3>是否允许子元素伸缩</h3>
```css
.item{
-webkit-box-flex: 1.0;
-moz-flex-grow: 1;
-webkit-flex-grow: 1;
flex-grow: 1;
}
```
```css
.item{
-webkit-box-flex: 1.0;
-moz-flex-shrink: 1;
-webkit-flex-shrink: 1;
flex-shrink: 1;
}
```
上面是允许放大，box语法中 box-flex 如果不是 0 就表示该子元素允许伸缩，

而flex是分开的，

上面  flex-grow 是允许放大（默认不允许），

下面的  flex-shrink 是允许缩小（默认允许）。

box-flex 默认值为0，也就是说，在默认的情况下，在新旧浏览器中的表现是不一样的：
<h3>子元素的显示次序</h3>
```css
.item{
-webkit-box-ordinal-group: 1;
-moz-order: 1;
-webkit-order: 1;
order: 1;
}
```
<a href="http://www.tuicool.com/articles/Yzeu6j7">参考链接</a>






















