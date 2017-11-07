# 动态内存分配

## 任务编号

`task3`

## 任务目的

熟悉`C/C++`的语法。
掌握`动态内存分配`、`计算机内存`的逻辑构造以及`指针`的简单用法。

## 任务要求

本次任务为算法题目，算法实现要求使用`C/C++`完成。同时还需要你提供一张原理图以证明你已经通过本次任务学会了所要求的知识。

## 任务时间

2017-11-12 至 2017-11-26
**注： 起始时间为我们开始Review的时间，终止时间为Review的截止时间。**

## 题目：

1. 显示float数据的二进制形式。
2. 动态分配内存并操作这段内存以输出这段内存的内容。

## 描述：

1. 在C/C++中，float类型的数据是按照IEEE 754标准以二进制形式存储的，平时我们编写程序的时候并不能看到float类型的二进制形式，换言之它对于程序员而言是透明的。现在请你想办法输出float类型数据的十六进制形式（等价于二进制）：

   > 提示：
   >
   > 1. 思考如何用`cout`输出数据的二进制形式；
   > 2. 思考指针的实际意义，高级语言中的“类型”究竟在内存中是一个怎样的模型。

   在完成这个题目之后，请选择一个float数据，写出它的二进制形式，并按照IEEE 754的标准把每个部分代表的内容都标记出来，要求写出过程。相应的文本保存为`float_binary.txt`。

   如：

   >**176.0625**
   >
   >1）将176.0625的整数部分和小数部分分别转化为二进制：
   >
   >> 176 =0b10110000
   >> 0.0625=0b0.0001
   >
   >则176.0625的二进制为：0b10110000.0001；
   >
   >2）IEEE754约定小数点左边隐含1位，通常为1，因此
   >
   >0b10110000.0001=0b1.01100000001 * 2^7；
   >
   >3）IEEE754约定单精度指数偏移量为127，所以176.0625使用IEEE754标准表示时，指数偏移量为7+127=134=0b10000110；
   >
   >4）IEEE754约定单精度尾数长度为23，所以176.0625使用IEEE754标准表示时，尾数为0b01100000001000000000000；
   >
   >5）176.0625>0,即为整数，所以符号位为0；
   >
   >6）故使用IEEE754规格化后的表示为：
   >
   >0b 0 	 	 10000110 	  01100000001000000000000
   >
   >​     符号位	 指数偏移	  尾数

2. C语言中的`malloc`函数以及C++中的`new`操作符都能够在程序的执行过程中动态分配一段内存，动态分配内存能够让我们更加灵活地操作操作系统的内存而不必依赖于静态内存分配，同时也能节省内存。

   现在请你动态分配一段大小为**64 bits**的内存，并为这段内存中轮流填入相应的数据，同时用适当的操作来完成如下输出：

   > 第一轮：
   > [2147483647,-2147483648]
   >
   > 第二轮：
   > [65525, 65524, 65523, 65522]
   >
   > 第三轮：
   > [-128 , 34811, 256, 4294967295 ]
   >
   > 第四轮：
   > [‘A’, "hello!\0"]

   在完成这个题目之后，请你画出你分配的这段内存的结构简图，并标识出每一轮输出时，内存的数据内容（以**二进制**形式分段展示）。图片保存为`memory.png`

## 示范：

### 1、第一题

输入：

> 3.14159

输出：

>0x40490fd0

### 2、第二题

输入：

> 无

输出：

> 1st Round:
>
> [2147483647,-2147483648]
>
> 2nd Round:
>
> [65525, 65524, 65523, 65522]
>
> 3rd Round:
>
> [-128 , 34811, 256, 4294967295 ]
>
> 4th Round:
>
> [‘A’, "hello!\0"]

## 测试用例：

### 1、第一题

**算法需满足包括但不仅限于以下测试用例。**

> 0.88846546 -> 0x3f637279
> 15613.49871 -> 0x4673f5ff

### 2、第二题

**无**