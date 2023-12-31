# C#多线程

	多线程就是多个线程同时工作的过程，我们可以将线程看作是程序的执行路径，
	每个线程都定义了一个独特的控制流，用来完成特定的任务。
	如果您的应用程序涉及到复杂且耗时的操作，那么使用多线程来执行是非常有益的。
	使用多线程可以节省 CPU 资源，同时提高应用程序的执行效率，
	例如现代操作系统对并发编程的实现就用到了多线程。

## 线程生命周期
	线程生命周期开始于我们创建 System.Threading.Thread 类对象的时候，
	当线程被终止或完成执行时生命周期终止。

## 下面列出了线程生命周期中的各种状态：
	未启动状态：当线程实例被创建但 Start 方法未被调用时的状况；
	就绪状态：当线程准备好运行并等待 CPU 周期时的状况；
	不可运行状态：下面的几种情况下线程是不可运行的：
		已经调用 Sleep 方法；
		已经调用 Wait 方法；
		通过 I/O 操作阻塞。
		死亡状态：当线程已完成执行或已中止时的状况。
## 主线程
	在 C# 中，System.Threading.Thread 类用于处理线程，
	它允许在多线程应用程序中创建和访问各个线程。
	在多线程中执行的第一个线程称为主线程，当 C# 程序开始执行时，
	将自动创建主线程，而使用 Thread 类创建的线程则称为子线程，
	可以使用 Thread 类的 CurrentThread 属性访问线程。

## Thread 类中的属性和方法
下表列出了 Thread 类中一些常用的属性：
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
CurrentContext</td>
<td>
获取线程正在执行的上下文</td>
</tr>
<tr>
<td>
CurrentCulture</td>
<td>
获取或设置当前线程的区域性</td>
</tr>
<tr>
<td>
CurrentPrincipal</td>
<td>
获取或设置线程的当前负责人（对基于角色的安全性而言）</td>
</tr>
<tr>
<td>
CurrentThread</td>
<td>
获取当前正在运行的线程</td>
</tr>
<tr>
<td>
CurrentUICulture</td>
<td>
获取或设置资源管理器使用的当前区域性以便在运行时查找区域性特定的资源</td>
</tr>
<tr>
<td>
ExecutionContext</td>
<td>
获取一个 ExecutionContext 对象，该对象包含有关当前线程的各种上下文的信息</td>
</tr>
<tr>
<td>
IsAlive</td>
<td>
获取当前线程的执行状态</td>
</tr>
<tr>
<td>
IsBackground</td>
<td>
获取或设置一个值，该值表示某个线程是否为后台线程</td>
</tr>
<tr>
<td>
IsThreadPoolThread</td>
<td>
获取线程是否属于托管线程池</td>
</tr>
<tr>
<td>
ManagedThreadId</td>
<td>
获取当前托管线程的唯一标识符</td>
</tr>
<tr>
<td>
Name</td>
<td>
获取或设置线程的名称</td>
</tr>
<tr>
<td>
Priority</td>
<td>
获取或设置线程的调度优先级</td>
</tr>
<tr>
<td>
ThreadState</td>
<td>
获取当前线程的状态</td>
</tr>
</tbody>
</table>

下表列出了 Thread 类的一些常用的方法：
<table>
<tbody>
<tr>
<th>
方法名</th>
<th>
描述</th>
</tr>
<tr>
<td>
public void Abort()</td>
<td>
在调用此方法的线程上引发 ThreadAbortException，以终止此线程</td>
</tr>
<tr>
<td>
public static LocalDataStoreSlot AllocateDataSlot()</td>
<td>
在所有的线程上分配未命名的数据槽，为了获得更好的性能，请改用以 ThreadStaticAttribute 特性标记的字段</td>
</tr>
<tr>
<td>
public static LocalDataStoreSlot AllocateNamedDataSlot(string name)</td>
<td>
在所有线程上分配已命名的数据槽，为了获得更好的性能，请改用以 ThreadStaticAttribute 特性标记的字段</td>
</tr>
<tr>
<td>
public static void BeginCriticalRegion()</td>
<td>
通知主机执行将要进入一个代码区域，在该代码区域内线程中止或未经处理的异常的影响可能会危害应用程序域中的其他任务</td>
</tr>
<tr>
<td>
public static void BeginThreadAffinity()</td>
<td>
通知主机托管代码将要执行依赖于当前物理操作系统线程的标识指令</td>
</tr>
<tr>
<td>
public static void EndCriticalRegion()</td>
<td>
通知主机执行将要进入一个代码区域，在该代码区域内线程中止或未经处理的异常仅影响当前任务</td>
</tr>
<tr>
<td>
public static void EndThreadAffinity()</td>
<td>
通知主机托管代码已执行完依赖于当前物理操作系统线程的标识指令</td>
</tr>
<tr>
<td>
public static void FreeNamedDataSlot(string name)</td>
<td>
为进程中的所有线程消除名称与数据槽之间的关联。为了获得更好的性能，请改用以 ThreadStaticAttribute 特性标记的字段</td>
</tr>
<tr>
<td>
public static Object GetData(LocalDataStoreSlot slot)</td>
<td>
检索当前线程中指定的值。为了获得更好的性能，请改用以 ThreadStaticAttribute 特性标记的字段</td>
</tr>
<tr>
<td>
public static AppDomain GetDomain()</td>
<td>
返回当前线程运行的域</td>
</tr>
<tr>
<td>
public static AppDomain GetDomainID()</td>
<td>
返回应用程序域的唯一标识符</td>
</tr>
<tr>
<td>
public static LocalDataStoreSlot GetNamedDataSlot(string name)</td>
<td>
查找已命名的数据槽。为了获得更好的性能，请改用以 ThreadStaticAttribute 特性标记的字段</td>
</tr>
<tr>
<td>
public void Interrupt()</td>
<td>
中断处于 WaitSleepJoin 状态的线程</td>
</tr>
<tr>
<td>
public void Join()</td>
<td>
在继续执行标准的 COM 和 SendMessage 消息泵处理期间，阻塞调用线程，直到某个线程终止为止。此方法有不同的重载形式</td>
</tr>
<tr>
<td>
public static void MemoryBarrier()</td>
<td>
按如下方式同步内存访问：执行当前线程的处理器在对指令重新排序时不能采用先执行 MemoryBarrier 调用之后的内存存取，再执行 MemoryBarrier 调用之前的内存存取的方式</td>
</tr>
<tr>
<td>
public static void ResetAbort()</td>
<td>
取消为当前线程请求的 Abort</td>
</tr>
<tr>
<td>
public static void SetData(LocalDataStoreSlot slot, Object data)</td>
<td>
在当前正在运行的线程上的指定槽中为此线程的当前域设置数据。为了获得更好的性能，请改用以 ThreadStaticAttribute 特性标记的字段</td>
</tr>
<tr>
<td>
public void Start()</td>
<td>
开始一个线程</td>
</tr>
<tr>
<td>
public static void Sleep(int millisecondsTimeout)</td>
<td>
让线程暂停一段时间</td>
</tr>
<tr>
<td>
public static void SpinWait(int iterations)</td>
<td>
让线程等待一段时间，时间长短由 iterations 参数定义</td>
</tr>
<tr>
<td>
public static byte VolatileRead(ref byte address)<br>
public static double VolatileRead(ref double address)<br>
public static int VolatileRead(ref int address)<br>
public static Object VolatileRead(ref Object address)</td>
<td>
读取字段值。无论处理器的数目或处理器缓存状态如何，该值都是由计算机处理器写入的最新值</td>
</tr>
<tr>
<td>
public static void VolatileWrite(ref byte address, byte value)<br>
public static void VolatileWrite(ref double address, double value)<br>
public static void VolatileWrite(ref int address, int value)<br>
public static void VolatileWrite(ref Object address, Object value)</td>
<td>
立即向字段中写入一个值，并使该值对计算机中的所有处理器都可见</td>
</tr>
<tr>
<td>
public static bool Yield()</td>
<td>
终止当前正在调用的线程并执行另一个准备运行的线程（由操作系统选择将要执行的另一个线程）</td>
</tr>
</tbody>
</table>

## 创建线程
C# 是通过扩展 Thread 类来创建线程的，然后使用扩展的 Thread 类调用 Start() 方法开始执行子线程。

```c#
using System;
using System.Threading;

namespace c.biancheng.net
{
    class Demo
    {
        public static void CallToChildThread()
        {
            Console.WriteLine("执行子线程");
        }
      
        static void Main(string[] args)
        {
            ThreadStart childref = new ThreadStart(CallToChildThread);
            Console.WriteLine("在 Main 函数中创建子线程");
            Thread childThread = new Thread(childref);
            childThread.Start();
            Console.ReadKey();
        }
    }
}

```

## 销毁线程
Thread 类中提供了 Abort() 方法用于销毁线程，Abort() 方法会抛出一个 threadabortexception 异常来中止线程，这个异常不能被捕获

```c#
using System;
using System.Threading;

namespace c.biancheng.net
{
    class Demo
    {
        public static void CallToChildThread()
        {
            try{
                Console.WriteLine("执行子线程");
                // 计数到 10
                for (int counter = 0; counter <= 10; counter++)
                {
                    Thread.Sleep(500);
                    Console.WriteLine(counter);
                }
                Console.WriteLine("子线程执行完成");

            }catch (ThreadAbortException e){
                Console.WriteLine("线程终止：{0}", e);
            }finally{
                Console.WriteLine("无法捕获线程异常");
            }
        }
        static void Main(string[] args)
        {
            ThreadStart childref = new ThreadStart(CallToChildThread);
            Console.WriteLine("在 Main 函数中创建子线程");
            Thread childThread = new Thread(childref);
            childThread.Start();
            // 停止主线程一段时间
            Thread.Sleep(2000);
            // 现在中止子线程
            Console.WriteLine("在 Main 函数中终止子线程");
            childThread.Abort();
            Console.ReadKey();
        }
    }
}

```




