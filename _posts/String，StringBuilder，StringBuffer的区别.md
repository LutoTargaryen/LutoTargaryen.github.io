---
published: false
---
##概述

-String类中，字符串是通过final char value[]实现的，也就是说，一个字符串创建之后就已经是固定的无法操作了，之后对该字符串的操作实际上是重新创建了一个字符串，并将引用指向该字符串

-StringBuilder和StringBuffer继承自AbstractStringBuilder抽象类，该类中字符串是通过char[] value实现的，因此是可操作的。不同的是在StringBuffer中的方法加入了同步锁，实现了线程安全。

##资源消耗

-在创建一个StringBuffer的时候（以new StringBuffer（“str”））为例，在StringBuffer的构造器StringBuffer(String str)内，![]({{site.baseurl}}/_posts/str.PNG)
首先会调用父类（AbstractStringBuilder）的构造方法AbstractStringBuilder(int capacity)，这个capacity参数是str的长度（通过str.length()获取，而length（）方法内部通过返回char数组的length实现）+16（StringBuffer中默认字符数组长度是16），而AbstractStringBuilder（）构造器会将AbstractStringBuilder类中的char数组初始化为一个capacity长度的数组；之后StringBuffer构造器会调用StringBuffer类中的append(String str)方法（该方法重写了父类中的append方法），该方法首先会将字符数组toStringCache缓存设为空，之后通过super.append(str)调用父类的append方法，在该方法中，因为我们传入的参数不为空，所以if判断里面的不执行（后面详细说append方法），之后会调用ensureCapacityInternal(int minimumCapacity)为字符数组扩容（但是因为初始时count为0，所以该方法中的判断不成立）；



