### 关键字和宏定义
* [const用法](https://www.jb51.net/article/118141.htm)以及[const和define的区别](https://blog.csdn.net/zhang_yanx/article/details/77801851)
* [static用法](https://www.cnblogs.com/jhmu0613/p/7131997.htmlhttps://www.cnblogs.com/jhmu0613/p/7131997.html)
* [static成员函数为什么不声明为虚函数，或const，volitile](https://www.cnblogs.com/lakeone/p/5967548.html)
* **C++ static变量的初始化顺序？？？**
* [new/delete和malloc/free的区别](https://www.cnblogs.com/maluning/p/7944231.html)
* [free如何知道要释放的空间的大小](https://www.zhihu.com/question/302440083?rf=312690701)
* ***delete如何知道数组的长度***
* [operater new()重载]，[定位new]

  1.new和delete是C++运算符，一般说的重载就是重载oprerator new,operator new [],operator delete, operator delete[];
  2.有八种operator new和operator delete的重载形式，前面四种参数里没有nothrow_t类型，分配错误时会产生bad_alloc，后四种不会报错
  3.可以自定义，重载上述四种类型的operator new和operator delete,但是不能重载 void* new(size_t, void*)版本，因为该版本为标准库使用，即3定位new表达式构造一个对象时使用，重载的函数同样要使用定位new形式去调用。
  4.定位new运算符，传入一个指针参数时，表示在该指针处构造对象，相当于construct,但是该指针可以不是allocator分配的空间首地址
  
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
* [常量define,const,constexpr,enum]()
  * enum就是讲一组整数常量组织在一起，每一条都是一个常量表达式，C++11分为不限定作用域的每局类型和限定作用域的枚举类型，后者在enum之后加class,且需要使用作用域运算符调用。
* [const和constexpr区别](https://www.cnblogs.com/wangxiaobao/p/5966394.html)

### C/C++常见函数
* strcopy()和strncopy()
* strcopy()和memcopy()
* memcopy()和memmove()
* bzero()和memset()
* strlen()和sizeof()
* 其他的字符串处理函数

### sizeof()及内存对齐
* [sizeof()](https://www.cnblogs.com/huolong-blog/p/7587711.html)
  
  	* 32bit操作系统基本数据类型的大小：char(1byte) bool(1byte) short(2bytes) int(4bytes) long(4bytes) float(4bytes) long long(8bytes) double(8bytes) 指针(4bytes)
	* 64bit操作系统基本数据类型的大小：char(1byte) bool(1byte) short(2bytes) int(4bytes) long(8bytes) float(4bytes) long long(8bytes) double(8bytes) 指针(8bytes)
	* Sizeof 计算的是类中非静态成员的类型大小之和，与类中的构造函数，析构函数以及其他成员函数无关
	* 因为空类型也可以实例化对象，为了标记对象，空类型的对象占用1byte大小，而不是0byte
	* 当类中含有虚函数时，对象的大小需要加上虚函数指针的大小
	* 注意数据成员的对齐
	
	
### 构造函数，拷贝/移动构造，拷贝/移动运算符，析构函数
#### 构造函数和析构函数
* [构造函数和析构函数可以调用虚函数吗](https://blog.csdn.net/libaineu2004/article/details/85341029)(effective C++ #9)
* [构造函数的执行顺序以及在构造时发生了什么？]，[虚构函数的执行顺序]
  * 构造函数的执行顺序：
  
    1.如果类3内不含其它显示定义的构造函数，则由编译器生成合成的默认构造函数
    2.如果定义了构造函数，那么按照对象内部成员的声明顺序初始化对象成员，之后再执行构造函数体，对于常量成员，引用成员，必须在初始化序列中初始化对象，初始化列表中也可以设置默认参数，一般默认参数之后不能再跟非默认参数，如果某成员没有初始化列表值，但有类内初始值，则使用类内初始值初始化，否则的话，像算数类型的成员变量，其值是未定义的。
    
    *  默认构造函数的操作
    
    3.该默认构造函数可能是无意义的，也可能是有意义的，有意义的默认构造函数只是为了满足编译器的需要
    4.有意义的默认构造函数分为四种情况：
       1）类中有部分成员对象有有意义的构造函数
       2）类在继承体系，其基类含有默认构造函数
       3）类中有虚函数，编译器为了满足编译，需要在构造函数中初始化虚表指针，指向虚表，访问type_info从而进行运行期类型识别
       4）类中有虚基类时，为了访问虚基类中的成员变量，必须保存虚基类的指针
    5.在继承体系的构造函数中，派生类需要先执行基类的构造函数，之后才是自己的构造函数
    6.在合成构造函数期间，编译器在构造函数中插入了许多代码（如虚表指针，虚基类指针，类中成员对象的构造函数），这些插入代码都在用户定义的代码前
* explicit

  不允许隐式的类型转换
  防止编译器将具有单个参数的构造函数当成类型转换运算符。
*



  
  
  
  
  
  
  
  
  
  
