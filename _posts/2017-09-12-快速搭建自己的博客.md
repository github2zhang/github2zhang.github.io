---
layout:     post
title:      利用 GitHub Pages 快速搭建个人博客
subtitle:   hexo+github 搭建自己的个人博客
date:       2017-09-12
author:     lambert
header-img: img/home-bg-o.jpg
catalog: true
tags:
    - hexo
    - github
---
### 前言


### private 权限扩大

在 Swift 4 中，`extension` 可以读取 `private` 变量了。

Swift 3 中，如果将主体函数的变量定义为 `private`，则其 `extension` 无法读取此变量，必须将其改为 `filePrivate` 才可以。

### 单向区间

单向区间是一个新的类型，主要分两种：确定上限和确定下限的区间。直接用字面量定义大概可以写成 `…6`和 `2…`

例如

```swift
let intArr = [0, 1, 2, 3, 4]

let arr1 = intArr[...3] 	// [0, 1, 2, 3]
let arr2 = intArr[3...] 	// [3, 4]
```

```java
这是我在测试java
```

### 字符串改动


#### String 操作简化了

`String` 许多要通过 `.characters` 进行的操作，可以直接用 String 进行操作了。

例如：

```swift
let greeting = "Hello, 😜!"
// No need to drill down to .characters
let n = greeting.count
let endOfSentence = greeting.index(of: "!")!

```

#### 新增 Substring 类型


swift 4 为字符串片段新增了一个叫 `Substring` 的类型。

当你创建一个字符串的片段时，会产生一个 `Substring` 实例。`Substring` 与 `String` 用法相同， 因为子串和原字符串共享内存，所以对子串的操作快速而且高效。

```swift
let greeting = "Hi there! It's nice to meet you! 👋"
let endOfSentence = greeting.index(of: "!")! 

// 产生 Substring 实例
let firstSentence = greeting[...endOfSentence]
// firstSentence == "Hi there!"

// `Substring` 与 `String` 用法相同
let shoutingSentence = firstSentence.uppercased()
// shoutingSentence == "HI THERE!" 
```

但是要注意一个 `Substring` 保留从其生成的完整的 `String`值。 当您传递一个看似很小的 `Substring` 时，这可能导致意外的高内存开销。所以使用 `Substring`时，最好转化为 `String`.

```swift
let newString = String(substring)
```