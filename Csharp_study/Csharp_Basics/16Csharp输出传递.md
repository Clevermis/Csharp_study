	使用 return 语句可以从函数中返回一个值，
	但是使用输出传递则可以从函数中一次性返回多个值。
	输出传递与引用传递相似，
	不同之处在于输出传递是将数据从函数中传输出来而不是传输到函数中。

在 C# 中，需要使用 out 关键字来使用输出传递，下面通过示例来演示一下：

```c#
using System;

namespace c.biancheng.net
{
    class Demo
    {
        static void Main(string[] args){
            int val = 33;
            Demo Obj = new Demo();
            Console.WriteLine("调用函数之前 val 的值：{0}", val);
            Obj.getValue(out val);
            Console.WriteLine("调用函数之后 val 的值：{0}", val);
        }
        public void getValue(out int x){
            int temp = 11;
            x = temp;
            x *= x;
        }
    }
}

```

    调用函数之前 val 的值：33
    调用函数之后 val 的值：121

***
在使用输出传递时，也可以不为实参赋值，如下例所示：

```c#
using System;

namespace c.biancheng.net
{
    class Demo
    {
        static void Main(string[] args){
            int a, b;
            Demo Obj = new Demo();
            Obj.getValues(out a, out b);
            Console.WriteLine("调用函数之后 a 的值：{0}", a);
            Console.WriteLine("调用函数之后 b 的值：{0}", b);
        }
        public void getValues(out int x, out int y){
            Console.WriteLine("请输入第一个值： ");
            x = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("请输入第二个值： ");
            y = Convert.ToInt32(Console.ReadLine());
        }
    }
}
```

    请输入第一个值：
    123
    请输入第二个值：
    321
    调用函数之后 a 的值：123
    调用函数之后 b 的值：321