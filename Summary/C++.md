### 关键字和宏定义
* [const用法](https://www.jb51.net/article/118141.htm)以及[const和define的区别](https://blog.csdn.net/zhang_yanx/article/details/77801851)
* [static用法](https://www.cnblogs.com/jhmu0613/p/7131997.htmlhttps://www.cnblogs.com/jhmu0613/p/7131997.html)
* [static成员函数为什么不声明为虚函数，或const，volitile](https://www.cnblogs.com/lakeone/p/5967548.html)
* **C++ static变量的舒适化顺序？？？**
* [new/delete和malloc/free的区别](https://www.cnblogs.com/maluning/p/7944231.html)
* [extern C](https://www.cnblogs.com/carsonzhu/p/5272271.html)
* 宏定义[#define](https://www.cnblogs.com/fnlingnzb-learner/p/6903966.html),[#ifndef](https://www.cnblogs.com/qinduanyinghua/p/7679018.html)
* volitile关键字

       Volatile关键字是一种类型修饰符，编译器不对被修饰的变量进行优化，用volatile关键字声明的变量每一次访问时都会从变量的
       内存单元中取值，没有用volatile修饰过的变量被再次访问的时候可能从cpu的寄存器中取值(因为变量之前被访问过，保存到cpu
       的某个寄存器中)，之所以会从寄存器直接取值而不从内存中取值，是因为编译器优化代码的结果(访问cpu 寄存器比访问内存块的
       多)，之所以这么做是因为变量随时可能会经常变化。
* [inline,内联函数只是建议](https://www.cnblogs.com/fnlingnzb-learner/p/6423917.html),[虚函数可以inline吗](https://blog.csdn.net/flydreamforever/article/details/61429140)
* [define和inline](https://blog.csdn.net/wangliang888888/article/details/77990650)
* [malloc内存分配机制](https://blog.csdn.net/u012658346/article/details/51154615https://blog.csdn.net/u012658346/article/details/51154615)(使用了伙伴算法)以及[最大的能够分配的内存](https://www.zhihu.com/question/20836462/answer/16341442)(大于128k时就使用mmap()分配内存)
