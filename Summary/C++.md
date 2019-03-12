### 关键字和宏定义
* [const用法](https://www.jb51.net/article/118141.htm)以及[const和define的区别](https://blog.csdn.net/zhang_yanx/article/details/77801851)
* [static用法](https://www.cnblogs.com/jhmu0613/p/7131997.htmlhttps://www.cnblogs.com/jhmu0613/p/7131997.html)
* [static成员函数为什么不声明为虚函数，或const，volitile](https://www.cnblogs.com/lakeone/p/5967548.html)
* **C++ static变量的舒适化顺序？？？**
* [new/delete和malloc/free的区别](https://www.cnblogs.com/maluning/p/7944231.html)
* [free如何知道要释放的空间的大小](https://www.zhihu.com/question/302440083?rf=312690701)
* ***delete如何知道数组的长度***
* ***operater new()重载，定位new***
* [extern C](https://www.cnblogs.com/carsonzhu/p/5272271.html)
* 宏定义[#define](https://www.cnblogs.com/fnlingnzb-learner/p/6903966.html),[#ifndef](https://www.cnblogs.com/qinduanyinghua/p/7679018.html)
* volitile关键字，volitile不是线程安全的([参考1](https://blog.csdn.net/ysc1123/article/details/77890759)，[参考2](https://www.cnblogs.com/li-daphne/p/5583912.html))

       Volatile关键字是一种类型修饰符，编译器不对被修饰的变量进行优化，用volatile关键字声明的变量每一次访问时都会从变量的
       内存单元中取值，没有用volatile修饰过的变量被再次访问的时候可能从cpu的寄存器中取值(因为变量之前被访问过，保存到cpu
       的某个寄存器中)，之所以会从寄存器直接取值而不从内存中取值，是因为编译器优化代码的结果(访问cpu 寄存器比访问内存块的
       多)，之所以这么做是因为变量随时可能会经常变化,常用于访问底层硬件设备中的变量。
* [inline,内联函数只是建议](https://www.cnblogs.com/fnlingnzb-learner/p/6423917.html),[虚函数可以inline吗](https://blog.csdn.net/flydreamforever/article/details/61429140)
* [define和inline](https://blog.csdn.net/wangliang888888/article/details/77990650)
* [malloc内存分配机制](https://blog.csdn.net/u012658346/article/details/51154615https://blog.csdn.net/u012658346/article/details/51154615)(使用了伙伴算法)以及[最大的能够分配的内存](https://www.zhihu.com/question/20836462/answer/16341442)(大于128k时就使用mmap()分配内存)
* [***常量define,const,constexpr,enum***]()
* [const和constexpr区别](https://www.cnblogs.com/wangxiaobao/p/5966394.html)

### C/C++常见函数
* strcopy()和strncopy()
* strcopy()和memcopy()
* memcopy()和memmove()
* bzero()和memset()
* strlen()和sizeof()
* 其他的字符串处理函数

### sizeof()及内存对其
* [sizeof()](https://www.cnblogs.com/huolong-blog/p/7587711.html)
  
  	* 32bit操作系统基本数据类型的大小：char(1byte) bool(1byte) short(2bytes) int(4bytes) long(4bytes) float(4bytes) long long(8bytes) double(8bytes) 指针(4bytes)
	* 64bit操作系统基本数据类型的大小：char(1byte) bool(1byte) short(2bytes) int(4bytes) long(8bytes) float(4bytes) long long(8bytes) double(8bytes) 指针(8bytes)
	* Sizeof 计算的是类中非静态成员的类型大小之和，与类中的构造函数，析构函数以及其他成员函数无关
	* 因为空类型也可以实例化对象，为了标记对象，空类型的对象占用1byte大小，而不是0byte
	* 当类中含有虚函数时，对象的大小需要加上虚函数指针的大小
	* 注意数据成员的对齐

  
  
  
  
  
  
  
  
  
  
