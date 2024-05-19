# html

1. 如何理解html语义化

	提高了代码可读性，让人更容易读懂，也让机器更容易读懂

	比如语义化的html代码更容易让搜索引擎读懂，也就便于SEO（Search Engine Optimization）

2. 默认情况下，哪些html标签是块级元素，哪些是内联元素

	display: block/table; => div,p,h1~h6,ol,ul,li,table,...

	display: inline/inline-block; => span,input,button,img,...

# css

**布局**

1. 盒模型的宽如何计算

	标准盒模型的 width = contentWidth; offSetWidth = contentWidth + 2*paddingWidth + 2*borderWidth;

	怪异盒模型（box-sizing: border-box;）的 width = contentWidth + 2*paddingWidth + 2*borderWidth = offsetWidth;

2. 相邻元素的 margin-top 和 margin-bottom 会重叠，如果中间有内容为空的元素则直接忽略

```html
<p>111</p>
<p></p>
<p></p>
<p></p>
<p>222</p>

<p>111</p>
<p></p>
<p>333</p>
<p></p>
<p>222</p>
```

```css
p {
	font-size: 16px;
	line-height: 1;
	margin-top: 10px;
	margin-bottom: 15px;
}
```

// 111 和 222 相距 15px
// 111 和 333 相距 15px
// 333 和 222 相距 15px

3. margin 负值的问题

4. BFC 的理解和应用

	Block Format Context, 块级格式化上下文

	一块独立的渲染区域，内部元素的渲染不会影响边界以外的元素

	形成 BFC 的常见条件

		- eg: overflow: hidden; (只要 overflow 不是 visible)

		- ...

	BFC 的常见应用

		- 处理因元素设置浮动导致的元素脱离文档流从而影响边界以外的元素

5. PC 场景中常用的“圣杯布局/双飞翼布局”

	用于 PC 场景中的三栏布局

	需要让中间一栏最先加载和渲染（因为内容最重要）

	需要让两侧内容固定，中间内容随着宽度自适应

6. 响应式布局

	flex布局: https://www.ruanyifeng.com/blog/2015/07/flex-grammar.html

	px: 绝对长度单位，最常用

	rem: 相对长度单位，相对于根元素，常用于响应式布局

	em: 相对长度单位，相对于父元素，不常用

	于是就有了第 2 种响应式布局方案

		- media-query 根据不同的屏幕宽度设置根元素的 font-size

		- 使用 rem

	第 3 种响应式布局方案：vw/vh

		屏幕高度：window.screen.height

		网页视口高度：window.innerHeight,

			vh 即网页视口高度的 1/100

			vw 即网页视口宽度的 1/100

			vmax 取两者最大值，vmin 取两者最小值

		body高度：document.body.clientHeight

7. absolute 和 relative 分别依据什么定位

	relative 依据自身定位

	absolute 依据最近一层的定位元素(absolute,relative,fixed)或者 body 定位

8. 居中对齐有哪些实现方式

	水平居中：

		inline 元素：text-align: center;

		block 元素：margin: auto;

		absolute 元素：left: 50% + margin-left 负值

	垂直居中：

		inline 元素：令 line-height = height

		absolute 元素：top: 50% + margin-top 负值

		absolute 元素：top,right,bottom,left = 0 + margin: auto;

**图文样式**

9. line-height 的继承问题

	写具体数值如 30px 则继承该值

	写比例如 2 则继承该比例

	写百分比如 200% 则继承计算出来的值（考点）

---

css3动画（非面试重点）

