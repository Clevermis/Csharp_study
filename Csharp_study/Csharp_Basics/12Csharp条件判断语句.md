```C#

using System;

namespace c.biancheng.net
{
    class Demo
    {
        static void Main(string[] args){
            Console.WriteLine("请输入学生的成绩：");
            int num = Convert.ToInt32(Console.ReadLine());
            if(num < 0 || num > 100){
                Console.WriteLine("您输入的成绩有误！");
            }else if(num >= 0 && num < 60){
                Console.WriteLine("不及格");
            }else if(num >= 60 && num < 70){
                Console.WriteLine("及格");
            }else if(num >= 70 && num < 80){
                Console.WriteLine("中等");
            }else if(num >= 80 && num < 90){
                Console.WriteLine("良好");
            }else if(num >= 90 && num <= 100){
                Console.WriteLine("优秀");
            }
            Console.ReadKey();
        }
    }
}
```