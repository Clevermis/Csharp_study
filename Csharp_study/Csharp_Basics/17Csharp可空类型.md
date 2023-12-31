## C# nullable：可空类型

    data_type? variable_name = null;

其中，data_type 为要声明的数据类型，后面紧跟一个问号；
variable_name 则为变量的名称。

【示例】下面通过示例来演示可空类型的用法：
```c#
using System;
namespace c.biancheng.net
{
    class Demo
    {
        static void Main(string[] args){
            int? num1;
            int? num2 = 123;
            num1 = null;
        
            double? num3 = new double?();
            double? num4 = 3.1415926;
            bool? boolval = null;
            // 输出这些值
            Console.WriteLine("num1 = {0} \r\n num2 = {1} \r\n num3 = {2} \r\n num4 = {3} \r\n boolval = {4}", num1, num2, num3, num4, boolval);
            Console.ReadLine();
        }
    }
}

```



    运行结果如下：
    num1 =
    num2 = 123
    num3 =
    num4 = 3.1415926
    boolval =

## Null 合并运算符（??）
    在 C# 中 Null 合并运算符用于定义可空类型和引用类型的默认值。
    如果此运算符的左操作数不为 null，那么运算符将返回左操作数，否则返回右操作数。
        例如表达式a??b中，如果 a 不为空，那么表达式的值则为 a，反之则为 b。
    需要注意的是，Null 合并运算符左右两边操作数的类型必须相同，或者右操作数的类型可以隐式的转换为左操作数的类型，否则将编译错误。

【示例】下面通过示例来演示 Null 合并运算符的使用：

```c#
using System;
namespace c.biancheng.net
{
    class Demo
    {
        static void Main(string[] args){
            int? num1 = null;
            int? num2 = 123;
            int num3;
        
            num3 = num1 ?? 321;
            Console.WriteLine("num3 = {0}", num3);
            num3 = num2 ?? 321;
            Console.WriteLine("num3 = {0}", num3);
            Console.ReadLine();
        }
    }
}
```

    运行结果如下：
    num3 = 321
    num3 = 123