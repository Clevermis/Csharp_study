# 析构函数
    与《构造函数》类似，C# 中的析构函数（也被称作“终结器”）同样是类中的一个特殊成员函数，
    主要用于在垃圾回收器回收类实例时执行一些必要的清理操作。

C# 中的析构函数具有以下特点：
    析构函数只能在类中定义，不能用于结构体；
    一个类中只能定义一个析构函数；
    析构函数不能继承或重载；
    析构函数没有返回值；
    析构函数是自动调用的，不能手动调用；
    析构函数不能使用访问权限修饰符修饰，也不能包含参数。

析构函数的名称同样与类名相同，不过需要在名称的前面加上一个波浪号~作为前缀，如下所示：
```c#
class Car
{
    ~Car()  // 析构函数
    {

    }
}
```

【示例】结合前面介绍的构造函数，让我们来演示一下类中构造函数和析构函数的使用：
```c#
using System;
namespace c.biancheng.net
{
    class Demo
    {
        static void Main(string[] args) 
        {
            Student stu1 = new Student();
            Student stu2 = new Student();
        }
    }
    public class Student
    {
        public Student(){
            Console.WriteLine("类中的构造函数");
        }
        ~Student(){
            Console.WriteLine("类中的析构函数");
        }
    }
}

```

    运行结果如下：
    类中的构造函数
    类中的构造函数
    类中的析构函数
    类中的析构函数

    注意：析构函数不能对外公开，所以我们不能在析构函数上应用任何访问权限修饰符。