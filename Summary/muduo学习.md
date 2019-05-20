* TimeQueue
 * [timefd](https://www.cnblogs.com/wenqiang/p/6698371.html)
* TcpConnection
 * [Nagle算法](h
 * [TCP关闭时的整个ttps://blog.csdn.net/sinat_35261315/article/details/79392116)
 * [scatter/gather I/O](https://blog.csdn.net/u012432778/article/details/47323805)
 * 应用层心跳机制以及TCP Keep_alive
   * 引入应用层心跳和传输层心跳的[原因](https://blog.csdn.net/bjrxyz/article/details/71076442)
   * 应用层心跳和传输层心跳的[优缺点](https://blog.csdn.net/chrisnotfound/article/details/80112736)
* TcpServer流程](https://blog.csdn.net/u010087886/article/details/50764342)
 * [如何判断一个C++可执行文件是debug build还是release build](https://blog.csdn.net/zhangzq86/article/details/80840927),即判断可执行文件是-O0编译的还是-O2编译的
 * [直接使用静态库和使用源码编译的区别](https://blog.csdn.net/qq_41786318/article/details/82115230) 
 * [pimpl](https://www.cnblogs.com/joinclear/p/3908661.html)(point to implement)
   * 使用pimpl技法可以避免一些二进制兼容的问题，比如如果更新了一个class,那很有可能引起二进制兼容的问题
 * template:实例化，extern template显式实例化模板
 * Linux nm指令查看目标文件中的变量和符号
 * C++预处理会将include的库文件全部替换到相应位置然后整体去编译
 * 动态库：节省硬盘，节省内存，动态更新，但是更新版本如何与之前兼容
 
   静态库：运行速度快，库的依赖在编译时就已经决定
   
   动态库和静态库都要考虑在更新时如何实现二进制兼容
 
