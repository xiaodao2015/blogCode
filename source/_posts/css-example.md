---
title: css样例整理
date: 2017-08-10 11:42:38
tags: css
---
## “TRBL”原则
即Top/Right/Bottom/Left方向赋值。比如：
每个值之间用空格分隔。

```css
border-width:1 1 2 3
```
还有另一种简写形式
### 一个值
一个值时，表示四边都是这个值。
```css
border-style:solid;
```
### 两个值
两个值时，第一个值表示元素上下边框类型，第二个值表示左右边框类型。
```css
border-style:solid dotted;
```
### 三个值
三个值时，第一个值表示元素的**顶边**的类型，第二个值表示元素**左右**边框类型，第三个值表示元素**底部**边框类型。
```css
border-style:solid dotted dashed;
```
### 四个值
四个值，每个边都指定。

```css
border-style:solid dotted dashed inset;
```
## 不同浏览器前缀
|浏览器分类|浏览器|私有属性的前端缀|
|:-|:-|:-:|
|Gecko引擎内核的浏览器|Mozilla（常指Firefox浏览器）|-moz-|
|WebKit内核|Safari, Google Chrome,傲游3|-webkit-|
|Presto内核|Opera|-o-|
|KHTML内核|Konqueror|-khtml-|
|Trident内核|IE|-ms-|

## -prefix-free摆脱浏览器前缀麻烦
利用这个脚本，可以省略去掉浏览器的前缀，从而节约开发时间和维护成本。
>**作者**:Lea Verou
>地址：[-prefix-free](http://leaverou.github.io/prefixfree/ "官网地址")
>在页面的头部调用如下脚本,`<script src="http://leaverou.github.com/prefixfree/prefixfree.min.js"></script>`
>在link中，或是style中，或是dom元素的style中书写CSS3 code，或是jQuery .css()方法此脚本会自动补上需要的前缀，让响应的浏览器支持该CSS3属性。


