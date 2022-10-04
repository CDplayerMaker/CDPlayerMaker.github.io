---
title: 我觉得我今天再多写一行代码都会安然死去
date: 2022-05-11 19:16:44
tags: vue
---
### 2022/05/11 vue遇到的问题记录
根本不是vue遇到的问题，都是cd遇到的问题。
<!-- more -->

- **`:nth-child(an+b)`** 这个 [CSS 伪类](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)首先找到所有当前元素的兄弟元素，然后按照位置先后顺序从1开始排序，选择的结果为CSS伪类:nth-child括号中表达式（an+b）匹配到的元素集合（n=0，1，2，3...）。示例：
- **`box-shadow: 0 0 3px 2px rgba(194, 192, 192, 0.2);`**我喜欢的盒子阴影
- **`{{xxxx|xxx}}`**在vue里面后半部分是过滤器

```js
filters:{
            number:function(val){
                val=val>0?'+'+val :val;
                return val;
            }
        }
```

- **`font-weight:bold`**字体加粗

- **`<template>`**元素的内容，但这样做只是为了确保这些内容有效；但元素内容不会被渲染。

- vue项目运行的时候提示**`TypeError: compiler.plugin is not a function`**

​		solution：`npm add webpack@latest`安装最新版的webpack

