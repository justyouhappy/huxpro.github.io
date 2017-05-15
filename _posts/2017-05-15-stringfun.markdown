---
layout:     post
title:      "string.prototype常用方法中slice substr substring"
subtitle:   "比较一下优劣~"
date:       2017-05-15
author:     "Alan"
header-img: "img/post-bg-rwd.jpg"
catalog: true
tags:
    - 前端
    - 技术
    - javascript
---

> live like youself. 

## str.substr(start[, length])

提取字符串的一部分，不改变原字符串

参数

```
1.start :开始提取字符串的位置，若为负数，则重字符串末尾开始，str.substr(str.length-1) 等价于str.substr(-1);

2.Length :可选参数，截取字符串的长度，如不填则默认截取到字符串末尾

注：在旧环境(ie9以下)里，不支持start负索引，若不传值，则返回整个字符串，若length传入负值，则返回空值
```

---

## str.slice(beg[, end])

提取字符串的一部分，并返回这个新的字符串，不改变原字符串

参数

```
1.beg :从该索引处开始提取，如果值为负数，会被作为str.length+beg看待

2.end :可选参数，从该索引处结束提取，如果省略该参数，则默认str.length，如果值为负数，会被作为str.length+end看待

注：截取字符串不包含end位置的字符，无兼容性问题
```

---

## str.substring(indexStart[, indexEnd])

此方法返回一个字符串在开始索引到结束索引(不包括)之间的一个子集, 或从开始索引直到字符串的末尾的一个子集。

参数  

```
1.indexStart :一个 0 到字符串长度之间的整数。

2.indexEnd :可选。一个 0 到字符串长度之间的整数。
```

此处需要注意：

    1.如果indexStart等于indexEnd，返回一个空字符串

    2.如果省略indexEnd，则一直到字符串末尾
    
    3.如果任一参数小于0或者为NAN，则被当成0

    4.如果任意参数大于字符串长度，则被当作字符串长度

    5.如果indexStart大于indexEnd相当于调换参数

    6.不改变原字符串

---

## 总结

在传递正值参数情况下，slice 和 substring  行为是一致的

在传递负值参数情况下，slice方法是通过字符串长度相加，符合一般思维，substring()第二个参数转换为0会容易出问题，起始位置会容易变更，

substr方法负值情况下会出现IE兼容性问题。