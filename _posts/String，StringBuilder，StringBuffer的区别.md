---
published: false
---
##概述
-String类中，字符串是通过final char value[]实现的，也就是说，一个字符串创建之后就已经是固定的无法操作了，之后对该字符串的操作实际上是重新创建了一个字符串，并将引用指向该字符串

-StringBuilder和StringBuilder继承自AbstractStringBuilder抽象类，该类中字符串是通过char[] value实现的，因此是课操作的



