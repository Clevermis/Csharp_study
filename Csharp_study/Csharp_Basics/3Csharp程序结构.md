# C#程序结构
在讲解 C# 的基本语法之前，让我们先来了解一下一个简单的 C# 程序是由哪些部分构成的。一个 C# 程序主要包括以下几个部分：
- 命名空间声明；
- 一个类（class）；
- 类方法；
- 类属性；
- 一个 Main 方法；
- 语句和表达式；
- 注释。
*** 

``` C#
//using 关键字用来在程序中引入 System 命名空间，一个程序中可以有多个 using 语句。
using System;
//namespace 关键字用来声明一个命名空间，“c.biancheng.net”则是命名空间的名字。
namespace c.biancheng.net
{
    //class 关键字用来定义一个类
    class Program
    {
        //Main 函数是整个 C# 程序的入口
        static void Main(string[] args)
        {
            /*第一个C#程序*/
            //WriteLine 是 System 命名空间中定义的 Console 类里面的方法，用来输出一些消息。
            Console.WriteLine("Hello World!");
            //此行代码是针对 VS.NET 用户的，它会使程序进入等待状态，敲击键盘上的任意一个按键即可让程序继续运行。
            //之所以需要这行代码，是因为命令行窗口会在程序运行结束后自动关闭，这会导致我们想要输出的内容一闪而过，加入此行代码则可以避免这种情况。
            Console.ReadKey();
        }
    }
}
```

```C#

```

