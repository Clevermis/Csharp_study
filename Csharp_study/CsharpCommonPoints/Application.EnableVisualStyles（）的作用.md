Application.EnableVisualStyles（）的作用 定义：

public static void EnableVisualStyles () 

此方法为应用程序启用可视样式。

如果控件和操作系统支持视觉样式，则控件将以视觉样式进行绘制。

若要使 EnableVisualStyles 生效，必须在应用程序中创建任何控件之前调用它；EnableVisualStyles 通常是 Main 函数的第一行。

当调用 EnableVisualStyles 时，无需单独的清单即可启用可视化样式。

	[STAThread] 
	static void Main()

	{

	Application.EnableVisualStyles();
	Application.Run(new Form1());

	} 

简单的说就是让你的控件（包括窗体）显示出来。