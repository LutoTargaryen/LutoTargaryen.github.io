---
published: false
---
##概述

-String类中，字符串是通过final char value[]实现的，也就是说，一个字符串创建之后就已经是固定的无法操作了，之后对该字符串的操作实际上是重新创建了一个字符串，并将引用指向该字符串

-StringBuilder和StringBuffer继承自AbstractStringBuilder抽象类，该类中字符串是通过char[] value实现的，因此是可操作的。不同的是在StringBuffer中的方法加入了同步锁，实现了线程安全。

##StringBuffer的创建

-在创建一个StringBuffer的时候（以new StringBuffer（“str”））为例，在StringBuffer的构造器StringBuffer(String str)内，![]({{site.baseurl}}/_posts/str.PNG)
首先会调用父类（AbstractStringBuilder）的构造方法AbstractStringBuilder(int capacity)![AbstractStringBuilder.PNG]({{site.baseurl}}/_posts/AbstractStringBuilder.PNG)
，这个capacity参数是str的长度（通过str.length()获取，而length（）方法内部通过返回char数组的length实现）+16（StringBuffer中默认字符数组长度是16），而AbstractStringBuilder（）构造器会将数组初始化为一个capacity长度的数组；之后StringBuffer构造器会调用StringBuffer类中的append(String str)方法，该方法在StringBuffer结尾出插入str，并更改后的StringBuffer对象

##StringBuffer中的append方法
-该方法会在StringBuffer结尾出插入字符串，并返回更改后的StringBuffer对象

-



