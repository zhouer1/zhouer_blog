---
title: 清除浮动
description: 
slug: post4
date: 2024-05-24 21:55:00+0000
image: https://cdn.jsdelivr.net/gh/zhouer1/resource/img/post4_cover.png
categories:
    - note
tags:
    - 前端
    - css
weight: 1
---

一种实际情况：在一个父元素包含子元素的布局中，包含块高度需要自适应所以不能设置高度，子元素恰好因为布局需求设为浮动，由于浮动元素会脱离文档流，如果此时包含块没有设置高度，就会产生高度塌陷

这时浮动元素是对父元素产生了影响，浮动也可以对其他元素产生影响，主要看实际情况

所以，当**浮动元素对布局产生了和开发者的预期不同的影响时**，我们就需要清除浮动

清除浮动是清除**浮动导致的布局问题**，不是把浮动干掉

### 设置额外标签 + clear方式清除浮动

在浮动元素下方添加一个块级元素，设置clear: both

缺点：产生了额外的元素，造成语义混乱和性能浪费


### 创建BFC清除浮动

设置包含块display:none（实际上我们可以设置为不为visible的所有值），会创建一个BFC，达到清除浮动的效果

设置包含块为浮动，也可以创建BFC，解决这个问题

缺点：设置display和float都会对布局产生影响，这改变了父元素本身布局的”含义“，产生潜在隐患或者额外的CSS代码开销

关于BFC的一些问题，看看GPT给出的解释

![post4_1](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/post4_1.png)


![post4_2](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/post4_2.png)

总的来说，就是：

- 子元素和父元素分别设置浮动，会产生两个不同的BFC
- 计算BFC的高度时，浮动元素也参与计算

### 设置伪元素 + clear方式清除浮动

为包含块设置clearfix类

```css
.clearfix::after{
	content: '';
	display: block;
	clear: both;
}
```

这种方式确保了结构的语义化，对布局也没有直接影响，比较推荐

[封面链接](https://www.pixiv.net/artworks/115522629)
[ChatGPT镜像站友情链接](https://chat.liu.xyz/)