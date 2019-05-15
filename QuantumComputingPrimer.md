## 希尔伯特空间(Hilbert Space) 
复向量内积空间，即两个复数向量上的函数并返回一个标量的二元运算，它的结果是欧几里得空间的标准内积。
对于量子计算，一个量子系统的态空间一般用有限维度的Hilbert空间来表述，即可以用来表述量子系统的各种可能的量子态。

## 量子两个基本状态
**叠加态**与**纠缠态**是两个基本的量子状态，主要是基于量子叠加和量子纠缠的性质来进行特殊的计算。简单来说，所谓**量子叠加态就是一个量子能在同一时间处于两种不同属性0和1的状态**，而对于经典物理中，**一个粒子只能处于一种状态，如要么左旋，要么右旋**。所谓**量子纠缠态，简单来说，就是满足一定条件的情况下一个量子的行为将会影响到另一个量子的状态**。即其中一个量子被操作改变而发生状态变化时，比如**进行量子观测时，一个量子被观测为左旋。则另一个量子其状态立即发生相应的状态变化。而两个量子之间不存在一定相同或者相反的绝对规则**。因此两个被纠缠的粒子可以是状态相同，也可以是状态相反。

## 常用于量子计算的逻辑门

1. 对单量子进行操作的逻辑门
【泡利门系列】 

**【泡利-X 门(Pauli-X gate)】** 

泡利-X 门操作一个量子比特，相当于经典的**逻辑非门**。如操作前量子位为 $|1\rangle$则进过泡利X门操作后会换成 $|0\rangle$。反之则由$|0\rangle$换成 $|1\rangle$。 
其线代矩阵表示为： 
![](https://img-blog.csdn.net/20180420125300977?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xzdHRveQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

**【泡利-Y 门(Pauli-Y gate)】**

泡利-Y 门操作单一个量子比特。有点类似于复数操作。
其线代矩阵表示为：
![](https://img-blog.csdn.net/20180420125622300?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xzdHRveQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

**【泡利-Z 门(Pauli-Z gate)】**

泡利-Z 门操作单个量子比特。 这个门保留基本状态$|0\rangle$不变,将$|1\rangle$换成$-|1\rangle$。 
其线代矩阵表示为:
![](https://img-blog.csdn.net/20180420125901721?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xzdHRveQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

**【阿达马门(Hadamard Gate)】** 
阿达马门是只对一个量子比特进行操作的门。 在量子计算中，该逻辑门可以实现对$|0\rangle$或者$|1\rangle$进行操作，然后成为叠加态。 
![阿达马门](https://img-blog.csdn.net/20180419223507931?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xzdHRveQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

我们一般用$H(qubits[0])$或者$H(qubits[1])$来表示对量子位0或者1的状态进行执行阿达马门 H 操作，使其处于叠加状态。 
量子位$|0\rangle$操作为

![](https://img-blog.csdn.net/20180419224119138?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xzdHRveQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

量子位$|1\rangle$操作为

![](https://img-blog.csdn.net/20180419224152224?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xzdHRveQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

**同时，如果进行连续两次$H$计算，则相当于没有进行任何的逻辑运算**。

**【向位门(Hadamard Gate)】**

对量子操作，改变旋转向位。通常能够进行操作在Bloch球面上将比特水平旋转$90$度的操作门，我们称之为$S$门。即旋转矢基$\theta$为90度。 
此外还有$T$门，饶水平面上旋转$45$度。

![量子计算机的基本操作提供一个能量规划程序(一系列的$h$和$J$数值)，这样计算机找到最优开关配置（+1和-1） ](https://img-blog.csdn.net/20170622085130472)

建立一系列$h$和$J$值的一个能量规划程序，是非常困难和耗时的。但这可以通过量子编程来实现。

## 一个自我编程的计算机
例如：输入一些训练好的数据，让计算机去学习分类。一开始系统选择一个随机的能量规划方式（仅仅是一串$h$和$J$的变量），并且持续输入更多的训练数据让其进行自我调整。不过，量子计算机的不同在于它是概率性的，这也意味着它可能会返回多个答案，即，是不确定性的。这在复杂系统中是非常有用的。

![教导一个允许自我演化的量子芯片，允许系统将把资源规划程序调整到你所给出的示例完全选择正确为止。这一过程是大家熟知的“训练”或者“学习”阶段。](https://img-blog.csdn.net/20170622085230160)

![在通过逐步训练得到一个最佳能量规划程序后，系统通过分类从未见过的示例来解决现实世界的问题了。这被称作“测试”阶段 ](https://img-blog.csdn.net/20170622085315920)
