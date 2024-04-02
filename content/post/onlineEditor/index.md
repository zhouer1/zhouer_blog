---
title: 一种可视化组件实时转源码编辑功能的实现
description: 
slug: onlineEditor
date: 2024-1-4 00:00:00+0000
image: https://cdn.jsdelivr.net/gh/zhouer1/resource/img/cover.png
categories:
    - note
tags:
    - 前端
    - Vue
    - 低代码可视化大屏
    - 编辑器
weight: 1
---
### 前置条件

平台组件渲染思路：

- 平台以JSON形式对拖拽式组件进行语法层面的组织
- 平台维护一个config.js配置文件，里面是每个组件的JSON预定义信息
- 每向平台加入一个新的组件，手动对其进行JSON的预定义
- 实例化拖拽式组件时，通过某种规则，对预定义的配置文件中的组件JSON进行转义，转成Vue语法并进行渲染

### 基本思路

1. 点击按钮，展示编辑界面
2. 我们可以获取当前大屏画布上的所有组件的JSON信息
3. 将这些JSON信息转义为Vue源码
4. 将Vue源码展示在编辑器上
5. 修改Vue代码
6. 点击保存按钮，将Vue代码转义为JSON
7. 平台重新渲染画布

### saveVue方法

用户点击保存按钮，调用saveVue方法，方法主要完成以下处理

1. 通过MonacoEditor的getValue()API获取编辑器内Vue源码的内容
2. 通过vue-template-compiler库的parseComponent()方法对Vue源码进行解析，并转为SFC描述对象，从SFC对象中分别提取出template,script,style标签中的内容(内容均为字符串)
![parsedComponent](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/parsedComponent.png)

3. 通过vue-template-compiler库的compile()方法对template标签里的内容进行解析，并获取其ast
![ast](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/ast.png)

4. 提取ast中与大屏画布相关的属性，使用MergeDeepAttribute方法进行合并，提取ast中与平台定义的组件的对象语法格式相关的属性，使用buildConfig方法构建全新的组件JSON(这里是直接提取所有的，全部重新构建，并不关注'改动'而只关注'结果'，性能有待提升)
![handleAST](https://cdn.jsdelivr.net/gh/zhouer1/resource/img/handleAST.png)

5. 分别对script和style标签进行处理，如果有内容，将其添置于大屏画布JSON中，如果没有内容则不做处理
6. 关闭对话框，返回大屏画布页面，此时画布会重新渲染，组件被更新

