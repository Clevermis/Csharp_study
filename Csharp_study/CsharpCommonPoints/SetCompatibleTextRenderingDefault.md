## Application.SetCompatibleTextRenderingDefault(false)的作用



    1.作用:在应用程序范围内设置控件显示文本的默认方式(可以设为使用新的GDI+,还是旧的GDI)，true使用GDI+方式显示文本, false使用GDI方式显示文本。
    2.只能在单独运行窗体的程序中调用该方法；不能在插件式的程序中调用该方法。
    3.只能在程序创建任何窗体前调用该方法，否则会引发InvalidOperationException异常。

备注：
 - GDI+是GDI的下一个版本，它进行了很好的改进，并且易用性更好。GDI的一个好处就是你不必知道任何关于数据怎样在设备上渲染的细节，GDI+更好的实现了这个优点，也就是说，GDI是一个中低层API,你还可能要知道设备，而GDI+是一个高层的API，你不必知道设备。例如你如果要设置某个控件的前景和背景色，只需设置BackColor和ForeColor属性
     
## 编程模式的变化
    “GDI uses a stateful model, whereas GDI+ uses a stateless”——GDI是有状态的，GDI+是无无状态的。