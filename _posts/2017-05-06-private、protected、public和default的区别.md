---
layout:     post
title:      private、protected、public和default的区别
date:       2017-05-06
author:     毒药
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
	- java
---

**public**
	具有最大的访问权限，可以访问任何一个在classpath下的类、接口、异常等。
**protected**
	主要的作用就是用来保护子类的。它的含义在于子类可以用它修饰的成员，其他的不可以。
	**default**
	有时候也称为friendly，它是针对本包访问而设计的，任何处于本包下的类、接口、异常等，都可以相互访问，即使是父类没有用protected修饰的成员也可以。
	**private**
	访问权限仅限于类的内部，是一种封装的体现，例如，大多数成员变量都是修饰符为private的，它们不希望被其他任何外部的类访问。
	![这里写图片描述](https://img-blog.csdn.net/20180328163811635?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3J1bm5lcjE5MjA=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
	
注意：java的访问控制是停留在编译层的，也就是它不会在.class文件中留下任何的痕迹，只在编译的时候进行访问控制的检查。其实，通过反射的手段，是可以访问任何包下任何类中的成员，例如，访问类的私有成员也是可能的。

区别：

public：可以被所有其他类所访问

private：只能被自己访问和修改

protected：自身、子类及同一个包中类可以访问，同一包，子包非子类不可访问

default：同一包中的类可以访问，声明时没有加修饰符，认为是friendly。子包不可访问