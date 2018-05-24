---
layout:     post
title:      String,StringBuffer和StringBuilder的区别
subtitle:   String,StringBuffer和StringBuilder的区别
date:       2017-01-01
author:     毒药
header-img: img/post-bg-re-vs-ng2.jpg
catalog: true
tags:
    - java
---

1.三者在执行速度方面的比较：StringBuilder >  StringBuffer  >  String

2.String <（StringBuffer，StringBuilder）的原因

　　String：字符串<font color="red">常量</font>

　　StringBuffer：字符串<font color="red">变量</font>（**线程安全**）

　　StringBuilder：字符串<font color="red">变量</font>（**非线程安全**）

   String和StringBuffer的主要性能区别在于String是不可变的对象。所以在每次对String类型进行改变的时候等同于创建了一个新的String对象，然后将引用地址指向新的String对象，所以经常改变内容的字符串最好不要用String，因为每次生成对象都会对系统性能造成影响。当内存中无引用对象多了以后，JVM的GC就会开始工作，速度比较慢。
   StringBuffer,每次结果都会对StringBuffer对象本身进行操作，而不是生成新的对象然后改变对象引用。当字符串需要经常改变的情况下，推荐使用StringBuffer。
   
   3.一个特殊的例子：

```
String str = “This is only a” + “ simple” + “ test”;
StringBuffer builder = new StringBuilder(“This is only a”).append(“ simple”).append(“ test”);
```
这个时候，你会发现生成str的速度会比builder快很多。在JVM的眼中String str = “This is only a” + “ simple” + “test”;其实就是String str = “This is only a simple test”;，所以速度更快。

4.StringBuilder与 StringBuffer
	
   java.lang.StringBuffer 线程安全的可变字符序列，可将字符串缓冲区安全的应用于多线程，可以在必要时对这些方法进行同步。

   java.lang.StringBuilder 一个可变的字符序列是5.0新增的。此类提供一个与 StringBuffer 兼容的 API，但不保证同步。该类被设计用作 StringBuffer 的一个简易替换，用在字符串缓冲区被单个线程使用的时候（这种情况很普遍）。如果可能，建议优先采用该类，因为在大多数实现中，它比 StringBuffer 要快。两者的方法基本相同。