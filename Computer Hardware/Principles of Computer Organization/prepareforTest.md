# 考试相关
## 1 计算机概要与技术

### 课后题：
1. 将指令从符号码翻译成二进制码的程序是（ ）
   **A. 汇编器**   B. 链接器     C. 加载器    D. 编译器

2. CPU主要包括（　　）两大部分。  
  A.  ALU和数据通路   **B. 数据通路和控制器**
  C. ALU和控制器     D. 控制器和主存储器

3. 下列哪一项和CPU的运算速度关系不大（   ）  
    A. CPU主频 B. MIPS  C. CPI  **D. 主存频率**

4. 在评价计算机性能时,唯一能够被完全可靠测量的性能指标是**时间**;这一指标可以由**CPI**、**指令数** 和**时钟周期**三者的乘积计算。

5. 在评价计算机性能时用**响应时间**表示计算机完成某任务所需时间;用**吞吐率**表示计算机单位时间完成任务的数量。




## 2 指令：计算机的语言
>举例说明为什么在编写MIPS汇编语言程序时应避免使用$at寄存器？  
>
>答：伪指令使MIPS拥有比硬件实现的更为丰富的指令集。汇编器在将伪指令转换为MIPS指令时可能会用到$at寄存器，所以我们在编写MIPS程序时应该避免使用$at。  
如 伪指令 blt  $s1, $s2, label 在汇编时被转换为  
slt $at,$s1,$s2  
bne $at,$zero,label    

```
Aproc:
addi $sp,$sp,-12
sw $ra,8($sp)
sw $s1,4($sp)
sw $s0,0($sp)
```
>6. 在MIPS中条件分支的地址范围（K=1024）是多大（      ）  
  A. 地址在0~64K-1之间     
  B.地址在0~256K-1之间   
  C. 分支前后地址范围各大约32K  
    **D.分支前后地址范围各大约128K**






## 3 计算机的算术运算
1. ALU总是将减法运算转化为加法来实现，在计算0x01234567-0x00135790时，实际进行的运算是0x01234567 +  0xFFECA870。

   2、整数 -1 的补码是（ C ），假设用8位二进制表示，最高位为符号位。  
    A. 10000000         B. 10000001       
    C. 11111111       D. 11111110

   3、双符号位表示正溢的是（ B ）
    A. 00           B. 01            C. 10           D. 11
4. 浮点加减法运算对阶时，如果尾数右移1位，则阶码应 **加** 1。



## 4 处理器









|周期|R型指令|store(sw)|Load(lw)|beq|j|
|:-----:|:-----:|:---:|:----:|:----:|
|1.取值周期(IF)|IR = Memory[PC],</br>PC = PC + 4|同左|同左|同左|同左|
|2.译码和读寄存器周期(ID)|A = Reg [IR[25-21]],B = Reg [IR[20-16]]，ALUOut = PC + (sign-extend (IR[15-0]) << 2)|同左|同左|同左|同左|
|3.执行/地址计算周期(EX)|ALUOut = A op B|ALUOut = A + sign-extend(IR[15-0])|ALUOut = A + sign-extend(IR[15-0])|if (A ==B) then PC = ALUOut|PC = {PC [31-28],(IR[25-0]<<2)}|
|4.访存周期/R型指令写回周期(WB)|Reg[IR[15-11]] =ALUOut|Memory [ALUOut] = B|MDR = Memory[ALUOut]|||
|5.写回周期(WB)|||Reg[IR[20-16]] = MDR||||





## 5 存储层次结构

>##### 什么是虚拟机？
>
>虚拟机：
基本定义：通过**配置软件**,**扩充机器功能**后形成的一台计算机，而实际硬件在物理功能上并不具备这种语言功能。
>
>系统虚拟机：可以在本地硬件上运行不同的**指令集系统结构**，但它们都与硬件匹配。
一台运行多个虚拟机的计算机可以支持多个不同的操作系统
支持虚拟机的软件被称为**虚拟机监视器**（VMM）。

>##### 什么是虚拟存储器？
>##### 构造虚拟存储器的作用？  
>
>**虚拟存储器：一种将主存当作辅助存储器（如磁盘）的高速缓存的技术**  
>
>构造虚拟存储器的两个动机：
* 扩大编程空间，**消除主存容量对程序设计造成的影响**。
* 允许云计算在多个虚拟机之间有效而安全地共享存储器。



# 计算题

1.CPI   
2.CPI和指令条数  
3.CPI和阻塞时间  
4.浮点数换算  
5.浮点数加减法  
6.浮点数乘除法  
7.改进版乘法  


|


8.改进版除法
74/21
|步骤
9.cache相关的题目  
