## CSS3有哪些新特性？

新增选择器 p:nth-child(n){color: rgba(255, 0, 0, 0.75)}

弹性盒模型 display: flex;

多列布局 column-count: 5;

媒体查询 @media (max-width: 480px) {.box: {column-count: 1;}}

个性化字体 @font-face{font-family: BorderWeb; src:url(BORDERW0.eot);}

颜色透明度 color: rgba(255, 0, 0, 0.75);

圆角 border-radius: 5px;

渐变 background:linear-gradient(red, green, blue);

阴影 box-shadow:3px 3px 3px rgba(0, 64, 128, 0.3);

倒影 box-reflect: below 2px;

文字装饰 text-stroke-color: red;

文字溢出 text-overflow:ellipsis;

背景效果 background-size: 100px 100px;

边框效果 border-image:url(bt_blue.png) 0 10;

转换

- 旋转 transform: rotate(20deg);
- 倾斜 transform: skew(150deg, -10deg);
- 位移 transform: translate(20px, 20px);
- 缩放 transform: scale(.5);

平滑过渡 transition: all .3s ease-in .1s;

动画 @keyframes anim-1 {50% {border-radius: 50%;}} animation: anim-1 1s;

&nbsp;

## display: none; 与 visibility: hidden; 的区别

共同点：

- 它们都能让元素不可见。
- 但我们仍然可以通过 JavaScript 操作该元素，因为浏览器会解析 HTML 标签生成 DOM Tree。虽然一旦 `display: none;` 了，因此后续的布局、渲染工作自然没它什么事了，至于 DOM 操作还是可以的。
- 无法获取焦点，即使通过 tab 键也是没办法的。
- 不耽误 form 表单提交数据。表单提交时，依然会将隐藏的 input 元素的值提交上去。

区别：

- `display: none;` 会让元素完全从渲染树中消失，渲染的时候不占据任何空间；`visibility: hidden; `不会让元素从渲染树消失，渲染师元素继续占据空间，只是内容不可见。
- 父元素为 `display: none;`，子孙元素哪怕设为显示，也没用，会表现成为 `display: none;`。
父元素为 `visibility: hidden;`，而子元素可以设置为 `visibility: visible;` 是可以生效的。
- `display: none;` 的元素无法响应任何事件。而设置为 `visibility: hidden;` 的元素其子元素可以为 `visibility: visible;`，因此隐藏的元素有可能位于事件冒泡的路径上。所以可在冒泡阶段响应事件。
- display 变化时将触发 reflow；而 visibility 变化则不会，只会触发 repaint。
- 读屏器不会读取 display: none; 元素内容；会读取 `visibility: hidden` 元素内容。
- Transition 对 display 的变化无效；而对 visibility 的变化有效。
- CSS中的 counter 会忽略 `display: none;` 的元素。 而对 visibility 却不会忽略。

&nbsp;

## CSS优先级算法如何计算？

基本原则：

- 优先级就近原则，同权重情况下样式定义最近者为准
- 载入样式以最后载入的定位为准
- 优先级为: !important > id > class > tag important 比 内联优先级高

css定义的权重规则：

- 标签的权重为 1，class 的权重为 10，id 的权重为 100
- 如果权重相同，则最后定义的样式会起作用，但是应该避免这种情况出现

```
// 权重为1
div{
}
// 权重为10
.class1{
}
// 权重为100
#id1{
}
// 权重为100+1=101
#id1 div{
}
// 权重为10+1=11
.class1 div{
}
// 权重为10+10+1=21
.class1 .class2 div{}
```

&nbsp;

## 不定宽高的垂直水平居中

传送门：[「干货」CSS 不定宽高的垂直水平居中（最全 9 种）](https://github.com/micherwa/blogs/blob/master/articles/2019/06-12%20%E3%80%8C%E5%B9%B2%E8%B4%A7%E3%80%8DCSS%20%E4%B8%8D%E5%AE%9A%E5%AE%BD%E9%AB%98%E7%9A%84%E5%9E%82%E7%9B%B4%E6%B0%B4%E5%B9%B3%E5%B1%85%E4%B8%AD%EF%BC%88%E6%9C%80%E5%85%A8%209%20%E7%A7%8D%EF%BC%89.md)

&nbsp;

## 对BFC规范的理解？

block formatting context（块级格式化上下文）

一个页面是由很多个 Box 组成的,元素的类型和 display 属性,决定了这个 Box 的类型

不同类型的 Box，会参与不同的 Formatting Context（决定如何渲染文档的容器），因此 Box 内的元素会以不同的方式渲染，也就是说BFC内部的元素和外部的元素不会互相影响

&nbsp;

## 伪类与伪元素的区别

传送门： [「前端面试题系列3」伪类与伪元素的区别及实战](https://github.com/micherwa/blogs/blob/master/articles/2019/01-04%20%E3%80%8C%E5%89%8D%E7%AB%AF%E9%9D%A2%E8%AF%95%E9%A2%98%E7%B3%BB%E5%88%973%E3%80%8D%E4%BC%AA%E7%B1%BB%E4%B8%8E%E4%BC%AA%E5%85%83%E7%B4%A0%E7%9A%84%E5%8C%BA%E5%88%AB%E5%8F%8A%E5%AE%9E%E6%88%98.md)

&nbsp;

## box-sizing的用法

传送门： [盒子模型中的box-sizing](https://github.com/micherwa/blogs/blob/master/articles/2017/07-15%20%E7%9B%92%E5%AD%90%E6%A8%A1%E5%9E%8B%E4%B8%AD%E7%9A%84box-sizing.md)

&nbsp;

## 圣杯布局与双飞翼布局的原理以及实现

两者的实现效果类似，传送门：[「前端面试题系列2」如何实现一个圣杯布局？](https://github.com/micherwa/blogs/blob/master/articles/2018/12-23%20%E3%80%8C%E5%89%8D%E7%AB%AF%E9%9D%A2%E8%AF%95%E9%A2%98%E7%B3%BB%E5%88%972%E3%80%8D%E5%A6%82%E4%BD%95%E5%AE%9E%E7%8E%B0%E4%B8%80%E4%B8%AA%E5%9C%A3%E6%9D%AF%E5%B8%83%E5%B1%80%EF%BC%9F.md)

&nbsp;

## a标签上四个伪类的正确执行顺序

`L-V-H-A` ：link > visited > hover > active

&nbsp;

## 如何修改Chrome记住密码后自动填充表单的黄色背景？

产生原因：由于Chrome默认会给自动填充的input表单加上 input:-webkit-autofill 私有属性造成的

解决方案1：在form标签上直接关闭了表单的自动填充：autocomplete="off"

解决方案2：input:-webkit-autofill { background-color: transparent; }

&nbsp;

## 如果需要手动写动画，你认为最小时间间隔是多久？

16.7ms 多数显示器默认频率是60Hz，即1秒刷新60次

所以理论上最小间隔: 1s / 60 * 1000 ＝ 16.7ms

&nbsp;

## 一个高度自适应的div，里面有两个div，一个高度100px，另一个高度自适应

方案1： .sub { height: calc(100%-100px); }

方案2： .container { position:relative; } .sub { position: absolute; top: 100px; bottom: 0; }

方案3： .container { display:flex; flex-direction:column; } .sub { flex:1; }

&nbsp;

## 如果设计中使用了非标准的字体，要如何去实现？

- 图片替代
- web fonts在线字库，如Google Webfonts，Typekit 等等
- @font-face
