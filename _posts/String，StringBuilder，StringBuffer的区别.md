---
published: false
---
##概述

-String类中，字符串是通过final char value[]实现的，也就是说，一个字符串创建之后就已经是固定的无法操作了，之后对该字符串的操作实际上是重新创建了一个字符串，并将引用指向该字符串

-StringBuilder和StringBuffer继承自AbstractStringBuilder抽象类，该类中字符串是通过char[] value实现的，因此是可操作的。不同的是在StringBuffer中的方法加入了同步锁，实现了线程安全。

##资源消耗

-在创建一个StringBuffer的时候（以new StringBuffer（“str”））为例，在StringBuffer的构造器内，![str.PNG]({{site.baseurl}}/_posts/str.PNG)
首先会调用父类（AbstractStringBuilder）的构造方法AbstractStringBuilder(int capacity)，这个参数是“str”的长度（）



