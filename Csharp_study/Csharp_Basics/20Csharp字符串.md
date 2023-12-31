# C# String：字符串

在 C# 中，string（或 String）关键字是 System.String 类的别名，其中提供了定义字符串以及操作字符串的一系列方法，下面就来详细介绍一下。
## 1、声明和初始化字符串
可以使用以下方式来创建字符串

	为 String 类型的变量赋值一个字符串；
	使用 String 类的构造函数；
	使用字符串串联运算符+；
	通过检索属性或调用返回字符串的方法；
	通过调用格式化方法将值或对象转换为其字符串表示形式。

```c#
using System;

namespace c.biancheng.net
{
    class Demo
    {
        static void Main(string[] args) 
        { 
            // 使用常规字符串为字符串变量赋值
            string name = "C语言";
            // 声明一个字符串并初始化为空
            string str1 = "欢迎访问：" + name;
            Console.WriteLine("str1 的值为：" + str1);

            // 使用 System.String.Empty 定义一个空字符串
            string str2 = System.String.Empty;
            Console.WriteLine("str2 的值为：" + str2);

            // 使用 System.String 类
            System.String url = "http://c.biancheng.net";;
            Console.WriteLine("url 的值为：" + url);

            // 在局部变量中（即在方法体中）可以使用 var 来代替具体数据类型来定义变量
            var temp = "C#教程";
            Console.WriteLine("temp 的值为：" + temp);

            // 定义一个常量字符串
            const string str3 = "这是一个常量字符串";
            Console.WriteLine("str3 的值为：" + str3);

            // 使用字符串构造函数定义字符串
            char[] letters = { 'H', 'e', 'l', 'l', 'o' };
            // string[] letters = { "C","语","言"};
            string message = new string(letters);
            Console.WriteLine("message 的值为：" + message);
        }
    }
}

```
    运行结果如下：
    str1 的值为：欢迎访问：C语言
    str2 的值为：
    url 的值为：http://c.biancheng.net
    temp 的值为：C#教程
    str3 的值为：这是一个常量字符串
    message 的值为：Hello

## 2、String 类中的属性
String 类中提供了两个属性，如下表所示：
<table>
<tbody>
<tr>
<th>
属性</th>
<th>
描述</th>
</tr>
<tr>
<td>
Chars[Int32]</td>
<td>
获取指定字符在字符串中的位置</td>
</tr>
<tr>
<td>
Length</td>
<td>
获取当前 String 对象中的字符数（字符串的长度）</td>
</tr>
</tbody>
</table>

## 3、String 类中的方法
String 类中提供了许多用来操作字符串的方法
<table>
<tbody>
<tr>
<th>
方法</th>
<th>
描述</th>
</tr>
<tr>
<td>
Clone()</td>
<td>
返回对此 String 实例的引用</td>
</tr>
<tr>
<td>
Compare(String, String)</td>
<td>
比较两个指定的 String 对象，并返回一个指示二者在排序顺序中的相对位置的整数</td>
</tr>
<tr>
<td>
CompareOrdinal(String, String)</td>
<td>
通过比较每个字符串中的字符，来比较两个字符串是否相等</td>
</tr>
<tr>
<td>
CompareTo(String)</td>
<td>
将一个字符串与另一个字符串进行比较</td>
</tr>
<tr>
<td>
Concat(String, String)</td>
<td>
连接两个指定的字符串</td>
</tr>
<tr>
<td>
Contains(String)</td>
<td>
判断一个字符串中是否包含零一个字符串</td>
</tr>
<tr>
<td>
Copy(String)</td>
<td>
将字符串的值复制一份，并赋值给另一个字符串</td>
</tr>
<tr>
<td>
CopyTo(Int32, Char[], Int32, Int32)</td>
<td>
从字符串中复制指定数量的字符到一个字符数组中</td>
</tr>
<tr>
<td>
EndsWith(String)</td>
<td>
用来判断字符串是否以指定的字符串结尾</td>
</tr>
<tr>
<td>
Equals(String, String)</td>
<td>
判断两个字符串是否相等</td>
</tr>
<tr>
<td>
Format(String, Object)</td>
<td>
将字符串格式化为指定的字符串表示形式</td>
</tr>
<tr>
<td>
GetEnumerator()</td>
<td>
返回一个可以循环访问此字符串中的每个字符的对象</td>
</tr>
<tr>
<td>
GetHashCode()</td>
<td>
返回该字符串的哈希代码</td>
</tr>
<tr>
<td>
GetType()</td>
<td>
获取当前实例的类型</td>
</tr>
<tr>
<td>
GetTypeCode()</td>
<td>
返回字符串的类型代码</td>
</tr>
<tr>
<td>
IndexOf(String)</td>
<td>
返回字符在字符串中的首次出现的索引位置，索引从零开始</td>
</tr>
<tr>
<td>
Insert(Int32, String)</td>
<td>
在字符串的指定位置插入另一个字符串，并返回新形成的字符串</td>
</tr>
<tr>
<td>
Intern(String)</td>
<td>
返回指定字符串的内存地址</td>
</tr>
<tr>
<td>
IsInterned(String)</td>
<td>
返回指定字符串的内存地址</td>
</tr>
<tr>
<td>
IsNormalized()</td>
<td>
判断此字符串是否符合 Unicode 标准</td>
</tr>
<tr>
<td>
IsNullOrEmpty(String)</td>
<td>
判断指定的字符串是否为空（null）或空字符串（""）</td>
</tr>
<tr>
<td>
IsNullOrWhiteSpace(String)</td>
<td>
判断指定的字符串是否为 null、空或仅由空白字符组成</td>
</tr>
<tr>
<td>
Join(String, String[])</td>
<td>
串联字符串数组中的所有元素，并将每个元素使用指定的分隔符分隔开</td>
</tr>
<tr>
<td>
LastIndexOf(Char)</td>
<td>
获取某个字符在字符串中最后一次出现的位置</td>
</tr>
<tr>
<td>
LastIndexOfAny(Char[])</td>
<td>
获取一个或多个字符在字符串中最后一次出现的位置</td>
</tr>
<tr>
<td>
Normalize()</td>
<td>
返回一个新字符串，新字符串与原字符串的值相等，但其二进制表示形式符合 Unicode 标准</td>
</tr>
<tr>
<td>
PadLeft(Int32)</td>
<td>
返回一个指定长度的新字符串，新字符串通过在原字符串左侧填充空格来达到指定的长度，从而实现右对齐</td>
</tr>
<tr>
<td>
PadRight(Int32)</td>
<td>
返回一个指定长度的新字符串，新字符串通过在原字符串右侧填充空格来达到指定的长度，从而实现左对齐</td>
</tr>
<tr>
<td>
Remove(Int32)</td>
<td>
返回一个指定长度的新字符串，将字符串中超出长度以外的部分全部删除</td>
</tr>
<tr>
<td>
Replace(String, String)</td>
<td>
使用指定字符替换字符串中的某个字符，并返回新形成的字符串</td>
</tr>
<tr>
<td>
Split(Char[])</td>
<td>
按照某个分隔符将一个字符串拆分成一个字符串数组</td>
</tr>
<tr>
<td>
StartsWith(String)</td>
<td>
判断字符串是否使用指定的字符串开头</td>
</tr>
<tr>
<td>
Substring(Int32)</td>
<td>
从指定的位置截取字符串</td>
</tr>
<tr>
<td>
ToCharArray()</td>
<td>
将字符串中的字符复制到 Unicode 字符数组</td>
</tr>
<tr>
<td>
ToLower()</td>
<td>
将字符串中的字母转换为小写的形式</td>
</tr>
<tr>
<td>
ToLowerInvariant()</td>
<td>
使用固定区域性的大小写规则将字符串转换为小写的形式</td>
</tr>
<tr>
<td>
ToString()</td>
<td>
将其它数据类型转换为字符串类型</td>
</tr>
<tr>
<td>
ToUpper()</td>
<td>
将字符串中的字母转换为大写形式</td>
</tr>
<tr>
<td>
Trim()</td>
<td>
删除字符串首尾的空白字符</td>
</tr>
<tr>
<td>
TrimEnd(Char[])</td>
<td>
删除字符串尾部的空白字符</td>
</tr>
<tr>
<td>
TrimStart(Char[])</td>
<td>
删除字符串首部的空白字符</td>
</tr>
</tbody>
</table>

