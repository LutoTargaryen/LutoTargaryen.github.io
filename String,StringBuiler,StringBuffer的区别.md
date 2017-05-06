---
published: false
---
## String,StringBuilder,StringBuffer的区别
###概述：
-在Java中String是通过final char value[]实现的，也就是说，String创建之后就是不可更改的，对String的更改实际上是新建一共String并把变量的引用指向String，比较浪费资源。
-StringBuffer和StringBuiler继承自AbstractStringBuilder抽象类，在该类中字符串是通过char[] value实现的，所有是操作是在原字符串上操作的。
