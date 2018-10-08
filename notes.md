
%title: 有关知识的复习
%author: 孟逸白

\renewcommand{\vec}[1]{\mathbf{#1}}
\newcommand{\intd}{\mathrm{d}}

# 经典力学复习

经典力学根本上是使用伽利略时空观的牛顿力学。我们在经典力学中研究一些力学量（mechanical variables）以及其关系。力学量又称可观测量（observables）。考虑到在伽利略时空观中时间是个特殊的量，只是个参数，*不是*力学量。

## 质点力学

对一个质点而言，力学量有：

- $\vec{r}$：位移
- $\dot{\vec{r}}$：速度
- $\ddot{\vec{r}}$：加速度

在牛顿力学中，对单个质点的运动，位移二阶以上的导数是没有物理意义的。不过对有些体系，有某些力学量的二阶以上的导数是有意义的。

还有几个力学量：

- 动量
- 能量：一般指机械能。
- 角动量：对质点系，刚体尤为重要。注意力矩和角动量关系：$$\vec{M} = \frac{\intd L}{\intd t}$$

量子力学是经典力学的扩展，但没有颠覆其时空观。

## 刚体力学

刚体的定点运动可以分为以下三个参数：

- 进动 procession
- 章动 nutation
- 转动 spin：在量子力学中被作为了一个内禀的物理量所使用。

## 分析力学

分析力学，又名Hamilton-Lagrange力学。

### 最小作用量原理和拉格朗日方程

最小作用量原理（Hamilton原理）
$$
\delta S = 0
$$
是分析力学的重要原理。

作用量为：
$$
S = \int{L(q,\dot{q};t) \intd t}
$$
中$L$为Lagrangian，只显含广义位置（正则位置）和广义速度。注意这个*显含*是我们人为赋予的意义，$L$*是*动量的函数，只是*不是显含动量*而已。我们可以把$L$改写为
$$
L' = L'(q,p;t)
$$
只是这个时候其物理意义就不明显了。

可以通过最小作用量原理”推出”（逻辑上应该不能）拉格朗日方程：
$$
\frac{\partial L}{\partial q} = \frac{\intd}{\intd t}(\frac{\partial L}{\partial \dot{q}})
$$

过程如下。
$$
\delta S = \delta \int{L(q,\dot{q};t)\intd t} =\int{(\frac{\partial L}{\partial q}\delta q +\frac{\partial L}{\partial \dot{q}}\delta\dot{q})\intd t}  
$$
为了理解这个过程，可以吧$\delta q$理解为两个区别很小的函数之差：
$$
\delta q \to q'(t) - q(t)
$$
这个差当然也是函数啦。因此，
$$
\delta S = \int{(\frac{\partial L}{\partial q}\delta q +\frac{\partial L}{\partial \dot{q}}\frac{\intd }{\intd t}(\delta q))\intd t}  
$$
可以这么做是因为变分和微分算子的线性性。

分部积分，得出：
$$
\delta S = \int{(\frac{\partial L}{\partial q} - \frac{\intd }{\intd t}\{\frac{\partial L}{\partial \dot{q}}\})\delta q \intd t} +  \int{\intd(\frac{\partial L}{\partial \dot{q}} \delta q)} 
$$
注意到对$q$求变分的时候要求其起始位置一致，即$t = 0$ 和$t = t_{\text{end}}$时$\delta q = 0$。这样，第二项就为零啦。又$\delta q$可以是任意形式的小函数，因此只能要求前面的系数是零了，即拉格朗日方程。

在场论中也有类似的关系，只是要额外引入场变量：每处质点相对原位置的位移和速度。

### 哈密顿力学

引入哈密顿量
$$
H(q,p;t) = p_{\alpha}\dot{q}_{\alpha}(q,p;t) - L(q,p;t)
$$
中广义动量
$$
p = \frac{\partial L}{\partial \dot{q}}
$$
这个时候就要如上文改写$L$的显含关系，以保证$H$是广义位置和广义动量的函数。

可以推导出

\frac{\partial{H}}{\partial{q}} = - \dot{p}
\frac{\partial{H}}{\partial{p}} = \dot{q}

这两个一阶方程，和之前的一个二阶拉格朗日方程等价。

以上这些这些都是二阶的
$$
\vec{F} = m\vec{a}
$$
的变换和推广，但与之一直保持等价。

### Possion 括号

对任意力学量，都有：
$$
\frac{\intd f}{\intd t} = \frac{\partial f}{\partial t} + \{f,H\}
$$
中$\{f,H\}$为该力学量与哈密顿量的Possion括号。两个力学量之间的Posion括号定义为
$$
\{f,g\} = \frac{\partial f}{\partial q}\frac{\partial g}{\partial p} - \frac{\partial f}{\partial p}\frac{\partial g}{\partial q} 
$$
显然是反对称的一个二元算符。

# 数学的复习

## 分析

我们回顾一下Dirac $\delta$ 函数。$\delta$函数不是个通常意义上的函数，不过可以用泛函的方法严格的去理解。

其最重要的性质是
$$
\int_{-\infty}^{\infty} {\delta(x) dx} = 1
$$
适合用来描述集中在一点，但总量又有限的某种分布。质点，点电荷都可以用此来描述。其实，可以把$\delta$函数视为一个符号，只能在积分下使用。

更常用的性质是
$$
\int_{-\infty}^{\infty} {f(x)\delta(x) dx} = f(0)
$$

$\delta$函数可以看作一些函数序列的极限。比如正态分布：
$$
N(\mu,\sigma;x) = \frac{1}{\sqrt{2\pi} \sigma} \exp{ - (\frac{x-\mu}{\sigma})^2} 
$$
在$\mu = 0$，$\sigma \to \inf$的时候的极限。

一堆有偏移的$\delta$函数的和是梳状函数，信号处理中有用。

$\delta$函数是物理学家提出，数学家严格化的。

## 代数

对一般的二元运算，$$AB \neq BA$$，因此，提出q number 和 c number:

- q number: 不可对易
- c number: 运算可对易（commutable）

引入算符（operator）的概念。在量子力学中可以理解成抽象的矩阵，矩阵是算服在具体表象（写对了嘛？）下的具体形势

回顾一下，矩阵的运算：

- 转置
- 共轭（当然是复数啦）
- 本征值
- Hermite共轭：$A^{\dagger}$ 转置再共轭

回顾本征值方程：
$$
\hat{A} | \psi \big \rangle = A_n | \psi \big \rangle
$$
和矩阵的本征值方程类似，不过把\hat{A}$理解为向量更加合适。

- $A_n$：本征值（eigenvalue）；
- $| \psi \big \rangle$：本征态（eigenstate）/本征向量（eigenvector）

对易运算：
$$[\hat{A}, B] = AB - BA$$
反对易：
$$[A,B]_{+} = AB + BA$$

## 矢量分析

回顾Einstein求和约定：一个表达式，有相同的指标，就视为对该指标求和。当然，求和范围是根据需要决定的。
$$
A_{\mu}B_{\mu} = \sum_{\mu = 1}^{3}{A_{\mu}B_{\mu}}
$$

回顾Kroneker张量：

\delta_{\alpha\beta} = { 1 (\alpha = \beta) 0 else}

可以理解成一个分立的delta函数。

对求和的指标，称为“哑指标”，叫什么都可以。

回顾矢量的叉乘
$$
(\vec{A} \times \vec{B})_{\alpha} = \epsilon_{\alpha\beta\gamma}A_{\beta}B_{\gamma}
$$
中$\epsilon_{\alpha\beta\gamma}$是Levi-Civita符号。在三个指标是123的偶置换的时候为1，其他时候全部为0。

对称张量和反对称张量


