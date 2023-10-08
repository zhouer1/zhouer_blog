---
title: 浏览器，搜索引擎与搜索应用
description: 
slug: browser-se-app
date: 2023-10-08 00:00:00+0000
image: https://cdn.jsdelivr.net/gh/zhouer1/resource/img/Japanese_Chrome_Chan.jpg
categories:
    - note
tags:
    - 浏览器
weight: 1
---
## 定义

1. 浏览器：浏览器是一种用于访问和浏览互联网上网页和其他资源的软件应用程序。它充当用户与互联网之间的接口，提供了浏览网页、查看多媒体内容、填写表单、执行脚本等功能。浏览器通过解析网页的HTML、CSS和JavaScript代码，并将其呈现为用户可交互的界面。
2. 搜索引擎：搜索引擎是一种用于在互联网上搜索和查找信息的工具。它通过建立庞大的索引数据库，收集和存储互联网上的网页内容，并根据用户提供的关键词或查询条件，返回与之相关的搜索结果。搜索引擎使用复杂的算法和技术来评估和排序搜索结果，以提供最相关和有用的信息给用户。
3. 搜索应用：搜索应用通常是一种以搜索引擎为核心的移动应用。它们旨在为移动设备用户提供方便的搜索功能和其他相关功能。这些应用程序通常在移动设备的应用商店中可以找到，并且可以在智能手机和平板电脑等移动设备上安装和使用。这些应用程序通常具有与桌面版本搜索引擎相似的搜索功能，并且可能包括其他特定于移动设备的功能，如语音搜索、地理位置服务等。

## 举例

| 公司      | 浏览器         | 搜索引擎 | 搜索应用 |
| --------- | -------------- | -------- | -------- |
| Google    | Chrome         | Google   | Google   |
| Microsoft | Microsoft Edge | Bing     | Bing     |
| Apple     | Safari         | Apple    | 暂无     |
| Mozilla   | Firefox        | 暂无     | 暂无     |
| 百度      | 百度浏览器     | 百度     | 百度     |
| Yahoo          |   暂无            |    Yahoo      |   Yahoo       |


## 关系

- 浏览器内置多个搜索引擎，且拥有默认的搜索引擎（一般是自家的）
- 搜索应用内置单个搜索引擎，且以搜索引擎为核心提供服务
- 搜索应用不能看作一个浏览器。虽然搜索应用可以展示网页搜索结果，但它的主要目的是提供搜索服务，而不是作为一个专门的浏览器。浏览器具有一系列特定的功能和特点，如渲染和显示网页内容、支持网页标准和技术、提供书签管理、历史记录、隐私保护等功能。相比之下，移动端搜索应用的重点是提供特定的服务功能，可能会缺少一些浏览器特有的功能和优化。尽管搜索应用可以进行搜索并展示网页，但由于其主要功能和设计重点的区别，它不能被直接称为一个浏览器。浏览器是专门用于浏览互联网的应用程序，而搜索应用更多地关注于特定的服务功能。

## 碎碎念

其实是我在群聊里面发现了一张精美的图片<span class="overlay" onmouseover="toggleOverlay(this)" onmouseleave="toggleOverlay(this)" ontouchstart="toggleOverlay(this)" ontouchend="toggleOverlay(this)">涩图</span>，于是想顺藤摸瓜找到图源和角色。但是，当我打开Chrome之后发现居然没有图片搜索功能。

想着浏览器没有这功能也能理解，于是搜索了“Google图片识别”，试图使用Google网页版直接搜图。

点击图片搜索按钮时，却顺理成章地给我跳到了GooglePlay的Google下载页面（手机上没有安装Google的搜索应用）。

![browser_img_1](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/browser_img_1.jpeg)

这个套娃让我顿感好奇<span class="overlay" onmouseover="toggleOverlay(this)" onmouseleave="toggleOverlay(this)" ontouchstart="toggleOverlay(this)" ontouchend="toggleOverlay(this)">恼羞成怒</span>，与此同时我也陷入了一种混乱之中：Chrome浏览器不是内置了Google搜索引擎吗，为什么还有Google这个应用？那Chrome里的Google是什么？Google又是什么？百度又是什么？我是谁我在哪......

于是我以实际情况作为问题询问了GPT：

![browser_gpt_1](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/browser_gpt_1.png)

GPT主要从设计哲学和用户体验的角度给出了解答，这可以作为很好的理由来解释为什么移动端的Chrome浏览器没有提供图片搜索功能。但是我发现我的疑惑远远没有这么简单，为什么在已经存在Chrome浏览器的情况下，手机上还有一个名叫“Google”的应用，Google不应该是一个搜索引擎吗？既然这样，为什么还存在这样一个同名的，类似浏览器的应用？

我首先验证了我对搜索引擎的认知：

![browser_gpt_2](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/browser_gpt_2.png)

看来，这个“Google”并不能被看作搜索引擎。既然如此，“Google”这个应用的存在就更让我疑惑了，我试图寻找它和Chrome的区别：

![browser_gpt_3](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/browser_gpt_3.png)

在这里，也许是因为同名给我造成了强烈的主观感受，我并不能很好地区分Google搜索引擎和Google应用这两个概念，即使GPT已经传达出了“Google其实是一个多功能聚合应用”这样的意思。我认为，浏览器就是浏览器，搜索引擎就是搜索引擎，而Google作为一个搜索引擎，却作为一个应用拥有了浏览器的特性，感觉十分混沌，让我并不能“清楚地”区分出它们的定义和边界，于是我又问了这样一个问题：

![browser_gpt_4](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/browser_gpt_4.png)

GPT给出了明确解答，Google应用并不能看作浏览器，虽然Google应用具备浏览器的一些功能，但是它们在构成和关注点上有很大的差别。我又继续追问了每天都在用的百度：

![browser_gpt_5](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/browser_gpt_5.png)

现在我似乎有点理解了情况，这些与搜索引擎同名的应用，它们既不能称为浏览器，又不能称为搜索引擎，它们是一类单独的应用，它们应该也有自己的名字。

![browser_gpt_6](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/browser_gpt_6.png)

原来，它们叫做“搜索应用”。

茅塞顿开之后，我又想到了一个问题：为什么这种搜索应用仅存在于移动端，而在电脑上我们一般都是直接通过浏览器进行搜索？

![browser_gpt_7](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/browser_gpt_7.png)

所有的疑惑，经过我的思考，分析，追溯，最终还是落到了一个点上，那就是**用户体验**。由于用户使用移动设备和电脑的具体情况有差异，为了因地制宜，为用户提供更好的使用体验，所以出现了这种小小的，甚至都不至于引起人们注意的产品之间的聚合与分化，也导致了我的“混乱”。

至此，这个不经意间诞生的疑惑，就这样结束了。

[ChatGPT镜像站友情链接](https://chat.liu.xyz/)

<script>
function toggleOverlay(element) {
  element.classList.toggle('clicked');
}
</script>
