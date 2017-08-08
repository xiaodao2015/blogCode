---
title: 选择器优先级
date: 2017-08-07 17:50:06
tags: css
---


样式表中同一元素可能有两个个或多个规则生效。哪种样式规则最终生效？这样就会产生冲突。[css](http://www.w3school.com.cn/css/css_syntax.asp)通过层叠处理这种冲突。层叠给每个规则分配一个重要度。页面引用的样式表是开发者编写的，被认为是最重要的样式表。浏览器使用的默认样式表，重要度是最低的。

## !important
!important提高样式的重要度。
层叠采用重要度次序：
* !important样式
* 用户样式
* 浏览器样式
* 两个规则特殊性相同，后定义的规则优先
## 特殊性

特殊性（优先级）可以用数值来表示。每种选择器都分配一个数值，将规则的每个选择器的值加在一起，计算出规则的特殊性。

选择器的特殊性分成4个等级，a、b、c、d。
* 如果样式是行内样式，那么a=1(千位).
* b等于id选择器的总数（百位）。
* c等于类、伪类和属性选择器的数量（十位）。
* d等于类型选择器和伪元素选择器的数量（个位）。
* \*所有选择器因为什么都代表，所以等于0。

>特殊性的计算不是以十位为基数计算的。采用的是一个更高的未指定的基数。这能确保不会被大量的id和类型选择器所超越。
但是为了简化，如果在一个特定选择器中的选择器数量少于10个，那么可以以10为基数计算特殊性。


**特殊性示例**

|*选择器*|特殊性|以10为基数的特殊性|
|:-|:-:|:-:|
|`style=""`|1,0,0,0|1000|
|`#id1 #id2{}`|0,2,0,0|200|
|`#id1 .class1{}`|0,1,1,0|110|
|`div #id1{}`|0,1,0,1|101|
|`#id{}`|0,1,0,0|100|
|`p.comment .class1{}`|0,0,2,1|21|
|`p.comment{}`|0,0,1,1|11|
|`div p{}`|0,0,0,2|2|
|`p{}`|0,0,0,1|1|

*举例猜猜看下面的代码`color`颜色*

```html
<html>
<body>
	<style>
		#content div#main-content h2{
			color:gray;
		}
		#content #main-content>h2{
			color:blue;
		}
		body #content div[id="main-content"] h2{
			color:green;
		}
		#main-content div.news-story h2{
			color:orange;
		}
		#main-content[class="news-story"] h2 {
			color:yellow;
			}
		div#main-content  div.news-story h2.first{
			color:red;
		}
	</style>
	<div id="content">
		<div id="main-content">
			<h2>这个是标题，也是测试目标</h2>
			<p>我的座椅好硬啊。</p>
			<div id="news-story">
				<h2 class="first">我也是测试的标题</h2>
				<p>垫的屁股疼。</p>
			</div>
		</div>
		
	</div>
</body>
</html>
```
*显示结果：*
{% asset_img code1.jpg 展示截图 %}
## 特殊性使用规则

> 为了避免样式表过于混乱，尽量保持一般样式非常一般，特殊样式尽可能特殊，这样就不需要覆盖特殊样式了。

## 附加
**伪类**
{% asset_img weilei.jpg 展示截图 %}
**伪元素（伪对象）**
{% asset_img Pseudo.jpg 展示截图 %}