## FreeRTOS下的SystemView

1. SEGGER SystemView 是什么？

> 观察OS的程序运行状态，深入、简单直接，特别适合多线程任务系统。
>
> 不需要增加其他额外的引脚、硬件，在工程（application)里面添加几个文件，就可以使用。
>
> ![SEGGER界面](https://img-blog.csdn.net/20171108004326764?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvYmpyMjAxNg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

2. 安装包

> 从http://www.segger.com/systemview.html下载最新的安装包并执行。安装向导会指引完成安装。 
> 安装完成之后，可以通过Windows开始菜单目录或者文件管理器访问程序包内容。
>
> PS：第一次进去之后，可以打开系统提供的symbol例子试试手。

3. 主要窗口

> Timeline
>
> > ![1575172489751](C:\Users\OXY\AppData\Roaming\Typora\typora-user-images\1575172489751.png)
> >
> > 此处可修改观测周期长度
>
> Events
>
> > 快捷键：
> >
> > 1. R
> >
> >    > 作用：方便我们对比时间节点
> >    >
> >    > 以当前时间为0点，往后的时间time_stamp以该点为标准
> >    >
> >    > 修改前：![1575172972367](C:\Users\OXY\AppData\Roaming\Typora\typora-user-images\1575172972367.png)
> >    >
> >    > 修改后：![1575173010561](C:\Users\OXY\AppData\Roaming\Typora\typora-user-images\1575173010561.png)
> >    >
> >    > PS：后面改变，前面没有变噢。再按一次R键，就会toggle反转恢复。
> >
> > 2. F
> >
> >    > 作用：跳到下一个周期的开始。（可以配合R键使用）
> >    >
> >    > 继续延伸上一个R键例子，当继续按了一次F。
> >    >
> >    > ![1575173259515](C:\Users\OXY\AppData\Roaming\Typora\typora-user-images\1575173259515.png)
> >    >
> >    > ↑数字这么整齐，明显可以推断出，两个函数间的周期间隔为10ms。
> >    >
> >    > 我们继续F一次看看。
> >    >
> >    > ![1575173339350](C:\Users\OXY\AppData\Roaming\Typora\typora-user-images\1575173339350.png)
> >    >
> >    > 噢，更加确定了周期10ms。
> >    >
> >    > 当我们尝试多几次的时候，会突然出现非10ms递增的情况
> >    >
> >    > ![1575173418127](C:\Users\OXY\AppData\Roaming\Typora\typora-user-images\1575173418127.png)
> >    >
> >    > 发生过中断。此时，我们看看IP_TASK上面，该进程在此次任务开始前，曾今进入过中断ETH_RX。
> >
> > 3. ctrl+G
> >
> >    > 跳到某个#节点



以上是12.1早上的简单总结，感兴趣的可以看文档：

1.官网的说明书：https://www.segger.com/products/development-tools/systemview/

2.csdn大牛中文翻译：https://blog.csdn.net/bjr2016

