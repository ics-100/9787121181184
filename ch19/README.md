## 19 两种典型的微处理器

**学习记录**

* `Tue Sep 15 18:03:55 CST 2020`


### 1 - 堆栈

* (last-in-first-out, LIF) 后进先出
* 通常把数据存入堆栈的过程称为压入(`push`), 把从堆栈取出数据的过程称作弹出(`pop`)
* 堆栈其实是一段普通的 RAM 存储空间，只是这段空间相对独立不另作他用
* 堆栈指针(SP, Stack Pointer), 一个专门的16位寄存器
* 堆栈上溢(stack overflow) / 堆栈下溢(stack underflow)


### 2 - 指令跳转

* 执行 `Call` 指令后，程序计数器加载一个新地址，而处理器会把原来的地址保存起来。
* 堆栈中保存的地址可以使处理器最后返回到转移之前的位置。用于返回的指令称为 `Return` 。
* Return 指令从堆栈中弹出两个字节，并把它们加载到 PC中

### 3 - 外围设备通信

* 外围设备实际上占用了一些通常用来寻址存储器的地址，这种结构称作内存映射I/O
* 增加地址专门用来访问输入/输出设备， 它们被称作 I/O端口
* 外围设备有时候需要获得处理器的注意。这个过程由一个称为中断的机制实现
* 在其执行的过程中也会把当前PC中的数据保存到堆栈