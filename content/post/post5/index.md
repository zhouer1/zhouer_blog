---
title: 字符串不可变
description: 
slug: post5
date: 2024-05-26 14:08:00+0000
image: https://cdn.jsdelivr.net/gh/zhouer1/resource/img/post5_cover.png
categories:
    - note
tags:
    - 前端
    - JavaScript
weight: 1
---

leetcode541，反转字符串Ⅱ，做题的时候遇到了问题：

```js
/**

 * @param {string} s

 * @param {number} k

 * @return {string}

 */

var reverseStr = function(s, k) {

    let n = s.length
    let start = 0
    let left = start
	let right = start + k - 1

    while(start < n){

        // 如果剩余字符少于 k 个，则将剩余字符全部反转
        if(right >= n) right = n - 1

        while(left < right){
            let temp = s[left]
            s[left] = s[right]
            s[right] = temp
            left++
            right--
        }

        start += 2*k
        left = start
        right = start + k - 1
    }
    
    return s
};
```

这段代码逻辑没有问题，但是不通过，根据调试结果显示，所有测试用例返回的字符串与输入相同，未被更改

因为刚刚才做了344题反转字符串，题目要求直接在字符串s上修改，所以没太在意，直接沿用了思路，后面仔细一对比才发现344题给出的是字符串数组，而这道题给出的是字符串

查资料发现JS的字符串**不可变**,不能直接对字符进行修改（怎么以前一直没注意到这个问题，不禁怀疑自己到底写了些什么代码...）


字符串不可变是由于字符串(string)在JavaScript中属于**原始值**

原始值不可变：JavaScript中的原始值（primitive values）包括字符串、数字、布尔值等，它们是不可变的。对原始值进行操作时，实际上是在创建一个新的值，而不是改变原始值本身
引用值可变：引用值（reference values）如对象和数组是可变的，因为它们存储的是引用（地址），可以直接修改对象或数组的内容

当我们对一个字符串进行操作时，比如拼接、裁剪、替换等，实际上是创建了一个新的字符串，原始字符串并没有被改变

如果要改变字符串的值，方式是创建一个新的字符串，并分配给原来的变量

```js
let str = 'Hi'
str = 'h' + str[1]
console.log(str) //hi
```
回到一开始的题，我们把字符串转为数组，处理之后再转回来，就可以通过了：

```js
var reverseStr = function(s, k) {

    let arr = [...s]
    let n = arr.length
    let start = 0
    let left = start
    let right = start + k - 1

    while(start < n){
        // 如果剩余字符少于 k 个，则将剩余字符全部反转
        if(right >= n) right = n - 1

        while(left < right){
            let temp = arr[left]
            arr[left] = arr[right]
            arr[right] = temp
            left++
            right--
        }

        start += 2*k
        left = start
        right = start + k - 1
    }

    return arr.join('')

};
```