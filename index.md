## 浅谈五种IO模型
今天去面试被问到常用的IO模型，虽然了解一点，但不是很清楚，回答的支支吾吾，当时恨不得拿块板砖往自己嘴上打两下:sweat_smile: 回去之后饿补了下，本文的主要内容翻译总结自《Unix Network Programming, Volume 1: The Sockets Networking API (3rd Edition)》by W. Richard Stevens  (Author), Bill Fenner (Author), Andrew M. Rudoff (Author)，6.2 I/O Models。

在UNIX网络编程中有五种IO模型：
1. 阻塞型I/O(blocking I/O)
2. 非阻塞型I/O(nonblocking I/O)
3. I/O多路复用(I/O multiplexing)
4. 信号驱动型I/O(signal driven I/O)
5. 异步I/O(asynchronous I/O)

在接下来的例子中，对于输入操作通常有两个不同的阶段：
1. 等待数据准备就绪
2. 将数据从内核拷贝到用户进程中

###1.阻塞型I/O
阻塞型I/O顾名思义，是进程的执行的阻塞型的，即当一个操作未完成之前，进程中其他的操作被阻塞，直到当前操作完成后才能执行下个操作，如下图所示。




