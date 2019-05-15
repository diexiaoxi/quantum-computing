## 希尔伯特空间(Hilbert Space) 
复向量内积空间，即两个复数向量上的函数并返回一个标量的二元运算，它的结果是欧几里得空间的标准内积。
对于量子计算，一个量子系统的态空间一般用有限维度的Hilbert空间来表述，即可以用来表述量子系统的各种可能的量子态。

## 量子两个基本状态
**叠加态**与**纠缠态**是两个基本的量子状态，主要是基于量子叠加和量子纠缠的性质来进行特殊的计算。简单来说，所谓**量子叠加态就是一个量子能在同一时间处于两种不同属性0和1的状态**，而对于经典物理中，**一个粒子只能处于一种状态，如要么左旋，要么右旋**。所谓**量子纠缠态，简单来说，就是满足一定条件的情况下一个量子的行为将会影响到另一个量子的状态**。即其中一个量子被操作改变而发生状态变化时，比如**进行量子观测时，一个量子被观测为左旋。则另一个量子其状态立即发生相应的状态变化。而两个量子之间不存在一定相同或者相反的绝对规则**。因此两个被纠缠的粒子可以是状态相同，也可以是状态相反。

## 常用于量子计算的逻辑门
每一个 Quantum Logic Gate都对应了一个数学上面的一个酉矩阵（Unitary Matrix）。如果 $n*n$ 的矩阵 $U$ 满足 $UU^{T}=U^{T}U=I$，那么 $U$ 就被称为酉矩阵。

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
其矩阵表示为：

![阿达马门](https://img-blog.csdn.net/20180419223507931?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xzdHRveQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

我们一般用$H(qubits[0])$或者$H(qubits[1])$来表示对量子位0或者1的状态进行执行阿达马门 H 操作，使其处于叠加状态。 
量子位$|0\rangle$操作为

![](https://img-blog.csdn.net/20180419224119138?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xzdHRveQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

量子位$|1\rangle$操作为

![](https://img-blog.csdn.net/20180419224152224?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xzdHRveQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

**同时，如果进行连续两次$H$计算，则相当于没有进行任何的逻辑运算**。

**【向位门(Hadamard Gate)】**

对量子操作，改变旋转向位。通常能够进行操作在Bloch球面上将比特水平旋转$90$度的操作门，我们称之为$S$门。即旋转矢基$\theta$为90度。 
此外还有$T$门，绕水平面上旋转$45$度。

2. 对双量子进行操作的逻辑门

## 【受控非门CNOT(Control-NOT gate)】**

第二个量子比特只有在第一个量子比特为$|1\rangle$的时候进行$NOT$操作，否则就保持不变。实际上，我们一般用这个逻辑门来对两个量子之间进行**纠缠处理**。而且因为是受控非门，因此我们可以控制受控量子对象的逻辑状态。

**【受控互换门SWAP(Swap gate)】** 

互换门操作两个量子比特，让两个量子比特相互交换量子位,即$SWAP(A,B)$。如果我们定义$A$的量子位为$|0\rangle$，$B$的量子位为$|1\rangle$，进过受控互换门操作后，则观测结果为$A$的量子位为$|1\rangle$，$B$的量子位为$|0\rangle$。

3. 对三量子进行操作的逻辑门

**【Toffoli门 CCNOT(Controlled-Controlled-NOT gate)】** 

Toffoli门是一个操作三个量子比特的的量子逻辑门，其为一种通用可逆逻辑门。 
主要表征为：$CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit):()$ 
其前两个量子比特是$|1\rangle$，则对第三个量子比特进行类似于经典的逻辑非门处理，反之则不做操作。前两个是操作子，后一个是观测子。 
整体输入输出表达式可以观测为以下： 

![](https://img-blog.csdn.net/20180420124705463?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xzdHRveQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

**【Fredkin门三位受控互换门CSWAP】**

在第一个量子比特是$|1\rangle$，且第二和第三个量子位不同时为$|1\rangle$的时候，后两个量子位相互交换。
整体输入输出表达式可以观测为以下： 

![](https://img-blog.csdn.net/20180420131459196?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xzdHRveQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

## 量子观测

每次观测，量子就会按照$|\alpha_0|^2$、$|\alpha_1|^2$的概率坍塌至$|0\rangle$或$|1\rangle$。量子存在一个 No-Cloning Theorem，这就导致了我们不能简单地“反复观测”量子计算的结果，而需要反复计算+观测。

## 量子克隆

![](https://i0.hdslb.com/bfs/article/1e609361ff1caa2fa9fe6cad2b8d48075c049df6.png@476w_256h.webp)

$$Ucn|X,0\rangle= |X,0\oplus X\rangle = |X,X\rangle$$,这是否意味着我们成功克隆了$|X\rangle$呢？

将$|X\rangle = a|0\rangle + b|1\rangle$代入:

 $$Ucn|X,0\rangle =Ucn(a|0\rangle+b |1\rangle)|0\rangle =  Ucn(a|00\rangle+b|10\rangle) = a|00\rangle+b|11\rangle$$

而我们想要得到的输出为

$$|X\rangle|X\rangle= (a |0\rangle+ b |1\rangle)(a|0\rangle+b|1\rangle) = a^2 |00\rangle+ab|01\rangle+ab|10\rangle+ b^2 |11\rangle $$

两者如果相等，那么$ab=0$并且$a,b=0$或$1$。
也就是说，如果想要克隆|X〉，那么要求需要克隆的qubit的所有可能态，属于一个集合${|\psi\rangle}$，这个集合中的态相互正交。我们无法做到对任意态的克隆。

反过来想，假设我们可以克隆任意qubit，那么我们就可以将1个qubit拷贝无数份，从而可以将$|X\rangle= a |0\rangle+ b |1\rangle$中的概率$a,b$精确到小数点后任意位，这意味着我们通过1个qubit传输了无穷多位经典bit，这是违反物理直觉的。



## 量子计算机

![量子计算机的基本操作提供一个能量规划程序(一系列的$h$和$J$数值)，这样计算机找到最优开关配置（+1和-1）](https://img-blog.csdn.net/20170622085130472)

建立一系列$h$和$J$值的一个能量规划程序，是非常困难和耗时的。但这可以通过量子编程来实现。

## 一个自我编程的计算机
例如：输入一些训练好的数据，让计算机去学习分类。一开始系统选择一个随机的能量规划方式（仅仅是一串$h$和$J$的变量），并且持续输入更多的训练数据让其进行自我调整。不过，量子计算机的不同在于它是概率性的，这也意味着它可能会返回多个答案，即，是不确定性的。这在复杂系统中是非常有用的。

![教导一个允许自我演化的量子芯片，允许系统将把资源规划程序调整到你所给出的示例完全选择正确为止。这一过程是大家熟知的“训练”或者“学习”阶段。](https://img-blog.csdn.net/20170622085230160)

![在通过逐步训练得到一个最佳能量规划程序后，系统通过分类从未见过的示例来解决现实世界的问题了。这被称作“测试”阶段 ](https://img-blog.csdn.net/20170622085315920)
