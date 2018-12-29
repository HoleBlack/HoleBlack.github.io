@[TOC]

## node是什么?
Node.js is a platform built on  Chrome's JavaScript runtime  for easily building fast, scalable network applications. Node.js 　　uses an event-driven, non-blocking I/O model that makes it lightweight and efficient, perfect for data-intensive real-time 　　applications that run across distributed devices.
可以看出
1.它是javaScript的运行环境可以更高效运行JS也具有一定的扩展性的软件
2. Node.js 事件驱动的 (什么叫事件驱动)、非阻塞的I/O模型(什么又叫非阻塞性模型?)
3. 非常适用于跨平台的数据密集设备的应用程序
4. 单进程,单线程

### 事件驱动
鼠标的一个点击，移动，键盘的按键按下等等操作，都是对应操作系统的一个事件，然后应用程序接受你的操作进行处理 

然后是百度的说明  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181228225454718.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5OTEyNTEx,size_16,color_FFFFFF,t_70)也就是对你所做的操作所进行的一系列过程和反响 但是这里没有包括返回来的结果 这个的重点在于对你的操作进行处理这个过程

### 非阻塞性I/O
关于这个:https://www.cnblogs.com/dolphin0520/p/3916526.html讲的非常详细很好,我就只提取关于非阻塞性I/O的回答了
Java中传统的IO都是阻塞IO，比如通过socket来读数据，调用read()方法之后，如果数据没有就绪，当前线程就会一直阻塞在read方法调用那里，直到有数据才返回；而如果是非阻塞IO的话，当数据没有就绪，read()方法应该返回一个标志信息，告知当前线程数据没有就绪，而不是一直在那里等待。

## node的安装
关于下载地址:https://nodejs.org/en/
然后改变下下载的路径就可以不停的下一步了
检查是否安装好 cmd中 node --version

## node如何用的?
我们还是老样子,首先以helloworld来进入新世界的大门
在node文件夹下随便建立一个以js文件结尾的文件(其实在哪建立都是可以执行的,我自己也试了,为了避免其他配置问题就在这个文件下面吧);
![在这里插入图片描述](https://img-blog.csdnimg.cn/2018122823452730.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5OTEyNTEx,size_16,color_FFFFFF,t_70)
然后控制台输入 node node.js 因为它是js文件 所以可以直接加载的
不同于java文件需要编译成为class文件然后 去运行
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181228234708175.png)

第二个实现的是用浏览器去访问
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181228234901430.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5OTEyNTEx,size_16,color_FFFFFF,t_70)listen括号中的可以随便写
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181228234932148.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5OTEyNTEx,size_16,color_FFFFFF,t_70)然后访问
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181228235159599.png)

## node的优缺点?

优点：
1. 高并发（最重要的优点）

2. 适合I/O密集型应用

缺点：

1. 不适合CPU密集型应用；CPU密集型应用给Node带来的挑战主要是：由于JavaScript单线程的原因，如果有长时间运行的计算（比如大循环），将会导致CPU时间片不能释放，使得后续I/O无法发起；

解决方案：分解大型运算任务为多个小任务，使得运算能够适时释放，不阻塞I/O调用的发起；

2. 只支持单核CPU，不能充分利用CPU

3. 可靠性低，一旦代码某个环节崩溃，整个系统都崩溃

原因：单进程，单线程

解决方案：（1）Nginx反向代理，负载均衡，开多个进程，绑定多个端口；

（2）开多个进程监听同一个端口，使用cluster模块；

4. 开源组件库质量参差不齐，更新快，向下不兼容

5. Debug不方便，错误没有stack trace

参考地址:https://www.cnblogs.com/hojo/p/5325352.html
