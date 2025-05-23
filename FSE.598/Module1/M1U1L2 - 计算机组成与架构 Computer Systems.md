
#### 1. 计算机五大模块
- **CPU**：
  - **(1)数据路径**：执行算术/逻辑运算，包含算术逻辑单元（ALU）和寄存器。
  - **(2)控制单元**：解读指令，指挥数据路径、内存和I/O设备。
- **(3)内存模块**：存储指令和数据，基于地址和内容。
- **(4)输入模块**：从键盘等设备接收数据，写入内存。
- **(5)输出模块**：从内存读取数据，发送到显示器等外部设备。
- **连接方式**：通过总线（属于其它基础设施）连接五大模块。
```note
运算器、控制器、存储器、输入设备、输出设备
```
#### 2. 计算机系统分层
- **半导体层**：晶体管基础。
- **电路层**：逻辑门（如与非门）。
- **寄存器传输层**：寄存器和总线传输。
- **模块层**：五大模块（CPU、内存、I/O）。
- **指令集层**：硬件与软件接口，定义机器码。（软硬件接口分界）
- **汇编语言层**：符号化机器码（如Intel、MIPS）。
- **高级语言层**：C++、Java、Python等。
- **系统软件层**：操作系统、编译器。
- **应用软件层**：游戏、文字处理等。

#### 3. 计算机架构与组成
- **架构（Architecture）**：指令集和汇编语言规范，定义软件-硬件接口。（包括部分模块层）
- **组成（Organization）**：模块层、寄存器传输层、逻辑门设计。
- **实现（Realization）**：半导体技术（如CMOS、TTL）。
- 分离架构与组成允许同一指令集支持不同性能/价格的硬件。

#### 4. 计算机发展里程碑
- **存储程序概念（冯诺依曼）**：程序和数据存储在内存，顺序执行（1945-48）。
- **计算机系列**：同一指令集，不同硬件实现（如IBM 360、Intel i3/i5/i7）。
- **流水线**：指令分阶段并行执行，接近1周期1指令。
- **多核**：多个处理器核心并行计算，提升性能。
- **CISC（复杂指令集）**：强大指令，适合汇编（如Motorola 68000、Intel 8086-486）。
- **RISC（精简指令集）**：简化指令，优化流水线（如MIPS、PowerPC、RISC-V）。

#### 5. 性能评估
- **用户视角**：响应时间 = CPU时间 + I/O等待 + 其他程序时间。
```
CPU时间=CPU 时钟周期 x 时钟周期时间 =CPU时间周期 / 时钟频率
```
- **CPU时间**：用户CPU时间（运行程序）+ 系统CPU时间（系统任务）。
- **性能定义**：速度 = 1 / 执行时间。
- **相对性能**：性能比 = 执行时间y / 执行时间x。
- **影响因素**：
  - **时钟频率**：提高频率（GHz）或缩短周期。
  - **指令周期数**：流水线优化，接近1周期/指令。不优化的话 MIPS大概是 5
- **摩尔定律**：集成电路元件数每18-24月翻倍，驱动性能提升。
  - DRAM容量：每年增长60%，每3年翻4倍。
  - CPU性能：1980-2002年每年增52%，2002年后因功耗墙降至20%，多核技术恢复增长。

#### 6. 编程模型与架构
- **累加器架构**：单一寄存器（累加器），运算一输入来自内存，另一来自累加器，结果回写累加器。
  - 例：`Y = x1*x2 + x3/x4`需7指令，14次内存访问。
- **堆栈架构**：数据先进后出，ALU从堆栈顶部取两数，结果推回顶部（如Java字节码）。
  - 例：8指令，13次内存访问。
- **内存-内存架构**：ALU直接从内存取两数，速度慢。
  - 例：4指令，15次内存访问。
- **加载-存储架构（RISC）**：数据先加载到寄存器，ALU只用寄存器数据，速度快（如MIPS、RISC-V）。
  - 例：8指令，5次内存访问。
- **CISC架构**：混合寄存器和内存操作，指令复杂。

#### 7. 案例：Java字节码（堆栈架构）
- 表达式：`Y = x1*x2 + x3/x4`（x1=3.0, x2=2.3, x3=4.5, x4=3.1416）。
- 步骤：
  - 加载x1、x2到堆栈，执行浮点乘法，结果推回堆栈。
  - 加载x3、x4，执行浮点除法，结果推回堆栈。
  - 执行浮点加法，结果存到y。
- 特点：无需显式参数，操作基于堆栈顶部。

#### 8. 关键规律与趋势
- **摩尔定律**：持续指导半导体发展，元件数翻倍推动内存和CPU性能提升。
- **功耗墙**：2002年后高频受限，多核技术弥补性能增长。
- **RISC优势**：简化指令，优化流水线，现代架构主流。
- **硬件-软件协同**：架构决定编程模型，汇编语言反映硬件特性。


