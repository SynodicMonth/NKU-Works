> 本笔记适用于对课上内容已有了解，但时间太久忘了（指考试前）的情况下复习用，不能作为初次学习的指导
> 本笔记基于《概率论与数理统计》浙江大学第四版
# 第一章 概率论的基本概念
## 随机试验
略
## 样本空间、随机事件 
$S$必然事件 $\varnothing$不可能事件
交换律：
$A \cup B = B \cup A, \ A \cap B = B \cap A$
结合律：
$A \cup (B \cup C) = (A \cup B) \cup C, \ A \cap (B \cap C) = (A \cap B) \cap C$
分配率：
$A \cap (B \cup C) = (A \cap B) \cup (A \cap C), \ A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$
德摩根律：
$\overline{A \cup B} = \overline A \cap \overline B, \ \overline {A \cap B} = \overline A \cup \overline B$
## 频率与概率
若集合函数$P$满足
 1. 非负性：$\forall A \in S,\  P(A) \geq 0$
 2. 规范性：$P(S) = 1$
 3. 可列可加性：$\forall A_1, A_2, \cdots \in S,\ P(\bigcup_{i=1}^{\infty} A_i) = \sum_{i=1}^{\infty} P(A_i)$
   
则称$P$为事件A的概率函数，记为$P(A)$
加法公式：$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$
## 古典概型
略
## 条件概率
条件概率的定义：
$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$
乘法原理：
$$P(A \cap B) = P(A|B)P(B)$$
全概率公式：
$$P(A) = \sum_{i=1}^n P(A|B_i)P(B_i)$$其中$B_1, B_2, \cdots, B_n$是$S$的一个划分
贝叶斯公式：
$$P(B_i|A) = \frac{P(A|B_i)P(B_i)}{\sum_{j=1}^n P(A|B_j)P(B_j)}$$
$$P(B|A) = \frac{P(A|B)P(B)}{P(A|B)P(B) + P(A|\overline B)P(\overline B)}$$
## 独立性
设$A$，$B$是$S$上的两个事件，若$P(A \cap B) = P(A)P(B)$，则称$A$，$B$相互独立。
# 第二章 随机变量及其分布
## 随机变量
略
## 离散型随机变量及其分布律
$$P\{X = x_i\} = p_i, \ i = 1, 2, \cdots, n$$
$p_i$满足如下两个条件
 1. $p_i \geq 0$
 2. $\sum_{i=1}^n p_i = 1$
### 0-1分布
$$P\{X = 1\} = p, \ P\{X = 0\} = 1 - p$$
### 二项分布
$$P\{X = k\} = C_n^kp^k(1-p)^{n-k}, \ k = 0, 1, \cdots, n$$
### 泊松分布
$$P\{X = k\} = \frac{\lambda^k e^{-\lambda}}{k!}, \ k = 0, 1, 2, \cdots$$
$b(n,p)$的二项分布可由$\lambda = np$的泊松分布近似
## 随机变量的分布函数
$$F(x) = P\{X \leq x\}, -\infty < x < \infty$$
称为随机变量$X$的分布函数，具有以下性质
 1. 不减性：$F(x) \geq F(y), \ x \leq y$
 2. $0 \leq F(x) \leq 1$，且$F(-\infty) = 0, F(\infty) = 1$
 3. $F(x)$是右连续的
## 连续型随机变量及其分布律
$$F(x) = \int_{-\infty}^x f(t)dt$$
$f(x)$满足如下性质：
 1. $f(x) \geq 0$
 2. $\int_{-\infty}^{\infty} f(x)dx = 1$
 3. $P\{a \leq X \leq b\} = \int_a^b f(x)dx$
 4. 若$f(x)$在$x$处连续，则$F'(x) = f(x)$
### 均匀分布
$$f(x) = \begin{cases} \frac{1}{b-a}, & a \leq x \leq b \\ 0, & x < a, x > b \end{cases}$$
$$F(x) = \begin{cases} 0, & x \leq a \\ \frac{x-a}{b-a}, & a \leq x \leq b \\ 1, & x \geq b \end{cases}$$
记为$U(a,b)$
### 指数分布
$$f(x) = \begin{cases} \lambda e^{-\lambda x}, & x \geq 0 \\ 0, & x < 0 \end{cases}$$
$$F(x) = \begin{cases} 0, & x \leq 0 \\ 1 - e^{-\lambda x}, & x > 0 \end{cases}$$
或令$\lambda = 1/\theta$，
$$f(x) = \begin{cases} \frac{1}{\theta} e^{-x/\theta}, & x \geq 0 \\ 0, & x < 0 \end{cases}$$
$$F(x) = \begin{cases} 0, & x \leq 0 \\ 1 - e^{-x/\theta}, & x > 0 \end{cases}$$
有无记忆性：
$$P\{X > s + t\ | \ X > s\} = P\{X > t\} = e^{-\lambda t}$$
### 正态分布
$$f(x) = \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$$
最大值为$\frac{1}{\sqrt{2\pi}\sigma}$，当$x = \mu$时取得
标准正态分布
$$\phi(x) = \frac{1}{\sqrt{2\pi}}e^{-\frac{x^2}{2}}$$
$$\Phi(x) = \int_{-\infty}^x \phi(t)dt$$
有$\Phi(-x) = 1 - \Phi(x)$
当$X \sim N(\mu, \sigma^2)$时，有$F(x) = \Phi\left(\frac{x-\mu}{\sigma}\right)$
$P\{a \lt X \lt b\} = \varPhi(\cfrac {b-\mu}\sigma) - \varPhi(\cfrac {a-\mu}\sigma), a \lt b$
$Hint:\ \int_{-\infty}^{\infty} e^{-x^2/2}dx = \sqrt{2\pi}$
## 随机变量的函数的分布
求$Y = g(X)$的分布律
定义法：
$$F_Y(y) = P\{Y \le y\} = P\{g(X) \le y\} = \displaystyle \int_{g(x) \le y} f_X(x)dx \\ f_Y(y) = F_Y'(y)$$
公式法：
若$g(x)$处处可导且恒有$g'(x)>0$（或$g'(x)<0$），$h(x)$是$g(x)$的反函数，则
$$f_Y(y) = \begin{cases} |h'(x)|f_X(h(y)), & \alpha \lt y \lt \beta \\ 0, & others \\ \end{cases}$$
其中$\alpha = min\{g(-\infty), g(\infty)\}, \beta = max\{g(-\infty), g(\infty)\}$
# 第三章 多维随机变量及其分布
## 二维随机变量
连续型
$$F(x,y) = P\{X \le x, Y \le y\}, -\infty \lt x \lt +\infty, -\infty \lt y \lt +\infty$$
离散型
$$P\{X = x_i, Y = y_j\} = p_{ij}, \ i,j = 1,2,3,\cdots \\ 
F(x, y) = \displaystyle \sum_{x_i \le x} \sum_{y_i \le y} p_{ij}$$
有如下性质：
 1. $0 \le F(x, y) \le 1$
 2. $F(-\infty,y) = F(x, -\infty) = F(-\infty, -\infty) = 0$
 3. $F(+\infty, +\infty) = 1$
 4. $P\{a \lt x \le b, c \lt y \le d\} = F(b,d) - F(b,c) - F(a,d) + F(a,c)$

概率密度函数
$$F(x, y) = \displaystyle \int_{-\infty}^x \int_{-\infty}^y f(u,v)dudv$$
有如下性质：
    1. $0 \le f(x, y) \le \infty$
    2. $\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f(x,y)dxdy = 1$
    3. $P\{a \lt x \le b, c \lt y \le d\} = \displaystyle \int_a^b \int_c^d f(x,y)dxdy$
    4. 若$f(x,y)$在$(x,y)$处连续，则$\frac{\partial^2 F(x,y)}{\partial x \partial y} = f(x,y)$
## 边缘分布
连续型
$$F_X(x) = P\{X \le x\} = F(x, +\infty) \\ 
F_Y(y) = P\{Y \le y\} = F(+\infty, y) \\
f_X(x) = \displaystyle \int_{-\infty}^{+\infty} f(x, y)dy \\
f_Y(y) = \displaystyle \int_{-\infty}^{+\infty} f(x, y)dx$$


离散型
$$p_{i \cdot} = P\{X = x_i\} = \displaystyle \sum_{i = 1}^{+\infty} p_{ij} \\ p_{\cdot j} = P\{Y = y_j\} = \displaystyle \sum_{j = 1}^{+\infty} p_{ij}$$
## 条件分布
连续型
$$f_{X|Y}(x|y) = \cfrac {f(x, y)}{f_Y(y)} \\
  f_{Y|X}(y|x) = \cfrac {f(x, y)}{f_X(x)} \\
  F_{X|Y}(x|y) = P\{X \le x | Y = y\} = \displaystyle \int_{-\infty}^x \cfrac {f(s, y)}{f_Y(y)} ds \\
  F_{Y|X}(y|x) = P\{Y \le y | X = x\} = \displaystyle \int_{-\infty}^y \cfrac {f(x, s)}{f_X(x)} ds$$
离散型
$$P\{X = x_i | Y = y_j\} = \cfrac {P\{X = x_i, Y = y_j\}}{P\{Y = y_j\}} = \cfrac {p_{ij}}{p_{\cdot j}} \\
P\{Y = y_j | X = x_i\} = \cfrac {P\{X = x_i, Y = y_j\}}{P\{X = x_i\}} = \cfrac {p_{ij}}{p_{i \cdot}}$$
## 相互独立的随机变量
离散型$X$和$Y$相互独立$ \iff F(x, y) = F_X(x)F_Y(y) \iff p_{ij} = p_{i \cdot} p_{\cdot j}$
连续型$X$和$Y$相互独立$ \iff F(x, y) = F_X(x)F_Y(y) \iff f(x, y) = f_X(x) f_Y(y)$
## 两个随机变量的函数的分布
$Z=X+Y$的分布
$$F_{X+Y}(z) = P\{X+Y \le z\} = \displaystyle \int_{-\infty}^{\infty} \int_{-\infty}^{z-y} f(x,y)dxdy \\ f_{X+Y}(z) = \displaystyle \int_{-\infty}^{\infty} f(z-y,y)dy = \displaystyle \int_{-\infty}^{\infty} f(x,z-x)dx$$
若X和Y相互独立，则
$$f_{X+Y}(z) = \displaystyle \int_{-\infty}^{\infty} f_X(z-y)f_Y(y)dy = \displaystyle \int_{-\infty}^{\infty} f_Y(z-x)f_X(x)dx$$
$Z=\frac{X}{Y},\ Z=XY$的分布
$$f_{Y/X}(z) = \displaystyle \int_{-\infty}^{\infty} |x|f(x,zx)dx \\
f_{XY}(z) = \displaystyle \int_{-\infty}^{\infty} \frac{1}{|x|} f(x,\frac{z}{x})dx$$
若X和Y相互独立，则
$$f_{Y/X}(z) = \displaystyle \int_{-\infty}^{\infty} |x|f_X(x)f_Y(zx)dx \\
f_{XY}(z) = \displaystyle \int_{-\infty}^{\infty} \frac{1}{|x|} f_X(x)f_Y(\frac{z}{x})dx$$
$M=max\{X,Y\},\ N=min\{X,Y\}$的分布
若X和Y相互独立，则
$$F_{max}(z) = P\{\max(X, Y) \le z\} = P\{X \le z, Y \le z\} = F_{X}(Z)F_{Y}(Z) \\
F_{min}(z) = 1-(1-F_{X}(Z))(1-F_{Y}(Z))$$
# 第四章 随机变量的数字特征
## 数学期望
$Y=g(X), Z=g(X,Y)$
离散型 
$$E(X) = \displaystyle \sum_{i = 1}^{+\infty} x_ip_i \\
E(Y) = E(g(X)) = \displaystyle \sum_{k = 1}^{+\infty} g(x_k) p_k \\
E(Z) = E(g(X, Y)) = \displaystyle \sum_{i = 1}^{+\infty} \sum_{j = 1}^{+\infty} g(x_i, y_j) p_{ij}$$
连续型 
$$E(X) = \displaystyle \int_{-\infty}^{\infty} xf(x)dx \\
E(Y) = E(g(X)) = \displaystyle \int_{-\infty}^{+\infty} g(x) f(x)dx \\
E(Z) = E(g(X, Y)) = \displaystyle \int_{-\infty}^{+\infty} \int_{-\infty}^{+\infty} g(x, y) f(x, y) dxdy$$
性质：
1. $E(C) = C$
2. $E(aX+bY) = aE(X)+bE(Y)$
3. X和Y相互独立，则$E(XY) = E(X)E(Y)$
## 方差
$$D(X) = E((X-E(X))^2) = E(X^2) - [E(X)]^2$$
性质：
1. $D(C) = 0$
2. $D(CX) = C^2D(X),\ D(X+C) = D(X)$
3. $D(X\plusmn Y) = D(X)+D(Y)\plusmn 2Cov(X, Y)$
4. X和Y相互独立，则$D(X+Y) = D(X)+D(Y)$

**契比雪夫不等式**
$$P\{|X-\mu| \ge \epsilon\} \le \frac{\sigma^2}{\epsilon^2} \\ 
P\{|X-\mu| < \epsilon\} \ge 1-\frac{\sigma^2}{\epsilon^2}$$
### 常见分布的期望与方差
|分布|符号|$E(X)$|$D(X)$|
|:-:|:-:|:-:|:-:|
|0-1分布|$Bi(p)$|$p$|$p(1-p)$|
|二项分布|$B(n, p)$|$np$|$np(1-p)$|
|几何分布|$Ge(p)$|$1/p$|$(1-p)/p^2$|
|均匀分布|$U(a, b)$|$(a+b)/2$|$(b-a)^2/12$|
|泊松分布|$P(\lambda)$|$\lambda$|$\lambda$|
|指数分布|$E(\lambda)$|$1/\lambda\ or\ \theta$|$1/\lambda^2\ or\ \theta^2$|
|正态分布|$N(\mu, \sigma^2)$|$\mu$|$\sigma^2$|
|卡方分布|$\chi^2(n)$|$n$|$2n$|
## 协方差及相关系数
$$Cov(X, Y) = E((X-E(X))(Y-E(Y))) = E(XY)-E(X)E(Y)$$
性质：
1. $Cov(X, C) = 0$
2. $Cov(aX, bY) = abCov(X, Y)$
3. $Cov(X_1 + X_2, Y) = Cov(X_1, Y) + Cov(X_2, Y)$
4. $Cov(X, Y) = Cov(Y, X)$
5. $Cov(X, Y) = 0 \Rightarrow X$和$Y$相互独立
6. $Cov(X, X) = D(X)$
7. $D(X\plusmn Y) = D(X)+D(Y)\plusmn 2Cov(X, Y)$

$$\rho_{XY} = \frac{Cov(X, Y)}{\sqrt{D(X)D(Y)}}$$
性质：
1. $|\rho_{XY}| \le 1$
2. $|\rho_{XY}| = 1 \iff X$和$Y$线性相关，即存在常数$a, b$使得$P\{Y=aX+b\}=1$
## 矩、协方差矩阵
$k$阶（原点）矩：$E(X^k)$
$k$阶中心矩：$E((X-E(X))^k)$
$X, Y$的$k+l$阶混合矩：$E(X^kY^l)$
$X, Y$的$k+l$阶中心混合矩：$E((X-E(X))^k(Y-E(Y))^l)$
协方差矩阵：
$$\boldsymbol C = \left( \begin{matrix} c_{11} & c_{12} & \cdots & c_{1n} \\ c_{21} & c_{22} & \cdots & c_{2n} \\ \vdots & \vdots & & \vdots \\ c_{n1} & c_{n2} & \cdots & c_{nn} \\ \end{matrix} \right)\ c_{ij} = \mathrm{cov}(X_i,X_j), \ c_{ij} = c_{ji} \\
\ \ \ \ \ \ \ = \begin{bmatrix} D(X_1) & Cov(X_1, X_2) & \cdots & Cov(X_1, X_n) \\ Cov(X_2, X_1) & D(X_2) & \cdots & Cov(X_2, X_n) \\ \vdots & \vdots & \ddots & \vdots \\ Cov(X_n, X_1) & Cov(X_n, X_2) & \cdots & D(X_n) \end{bmatrix}$$
# 第五章 大数定理及中心极限定理
## 大数定理
**弱大数定理（辛钦大数定理）**: 设$X_1, X_2, \cdots$是独立同分布的随机变量，且$E(X_i) = \mu$，则对任意$\varepsilon > 0$，当$n \to +\infty$时，有
$$\displaystyle \lim_{n \to +\infty} P \left\{ \left| \cfrac 1n \sum_{i=1}^n X_i - \mu \right| \lt \varepsilon \right\} = 1$$
**伯努利大数定理**：设$X_n\sim B(n,p)$，则对任意$\varepsilon > 0$，当$n \to +\infty$时，有
$$\displaystyle \lim_{n \to +\infty} P \left\{ \left| \cfrac {X_n}n - p \right| \lt \varepsilon \right\} = 1$$
## 中心极限定理
**列维-林德伯格中心极限定理**：设$X_1, X_2, \cdots$是独立同分布的随机变量，且$E(X_i) = \mu, D(X_i) = \sigma^2>0$，则对任意$x$，有
$$\displaystyle \lim_{n \to +\infty} P \left\{ \cfrac {\sum_{i=1}^n X_i - n\mu}{\sqrt{n} \sigma} \le x \right\} = \varPhi(x)$$
表明，当$n \to +\infty$时，$$\cfrac {\sum_{i=1}^n X_i - n\mu}{\sqrt{n} \sigma}\sim N(0,1)$$
$$\displaystyle \frac{\bar{X}-\mu}{\sigma/\sqrt{n}} \sim N(0,1)$$
**李雅普诺夫中心极限定理**：设$X_1, X_2, \cdots$是相互独立的随机变量，且$E(X_i) = \mu, D(X_i) = \sigma^2>0$，记$B_n^2 = \displaystyle \sum_{i=1}^n \sigma_i^2$，若存在正数$\delta$，使得$\displaystyle \lim_{n \to +\infty}\cfrac 1{B_n^{2+\delta}} \sum_{i = 1}^n E(|X_i - \mu_i|^{2+\delta}) = 0$，则有
$$\displaystyle \lim_{n \to +\infty} P \left\{ \cfrac {\sum_{i=1}^n X_i - \sum_{i=1}^n \mu_i}{B_n} \le x \right\} = \varPhi(x)$$
表明，当$n \to +\infty$时，$$\cfrac {\sum_{i=1}^n X_i - \sum_{i=1}^n \mu_i}{B_n}\sim N(0,1)$$
**棣莫弗-拉普拉斯中心极限定理**：设$X_n \sim B(n,p)$，则对任意$x$，有
$$\displaystyle \lim_{n \to +\infty} P \left\{ \cfrac {X_n - np}{\sqrt{np(1-p)}} \le x \right\} = \varPhi(x)$$
表明，当$n \to +\infty$时，$$\cfrac {X_n - np}{\sqrt{np(1-p)}}\sim N(0,1)$$
# 第六章 样本及抽样分布
## 随机样本
略
## 直方图和箱线图
略
## 抽样分布
**样本平均值**：
$$\bar{X} = \cfrac 1n \sum_{i=1}^n X_i$$
**样本方差**：
$$S^2 = \cfrac 1{n-1} \sum_{i=1}^n (X_i - \bar{X})^2 = \cfrac 1{n-1} \left (\sum_{i=1}^n X_i^2 - n\bar{X}^2\right)$$
**样本标准差**：
$$S = \sqrt{S^2} = \sqrt{\cfrac 1{n-1} \sum_{i=1}^n (X_i - \bar{X})^2}$$
**样本k阶原点矩**：
$$A_k = \cfrac 1n \sum_{i=1}^n X_i^k$$
**样本k阶中心矩**：
$$B_k = \cfrac 1n \sum_{i=1}^n (X_i - \bar{X})^k$$
注：$A_1 = \bar{X},\ B_2 \neq S^2$
### $\chi^2$分布
设$X_1, X_2, \cdots, X_n$是相互独立的随机变量，且$X_i \sim N(0,1)$，则称
$$\displaystyle \chi^2 = \sum_{i=1}^n X_i^2$$
为自由度为$n$的$\chi^2$分布，记为$\chi^2(n)$
性质:
1. $\chi^2 \sim \chi^2(n), E(\chi^2) = n, D(\chi^2) = 2n$
2. $\chi_1^2 \sim \chi_1^2(n_1),\ \chi_2^2 \sim \chi_2^2(n_2)$，且$\chi_1^2$，$\chi_2^2$相互独立，则$\chi_1^2 + \chi_2^2 \sim \chi^2(n_1 + n_2)$
### t分布
设$X, Y$是相互独立的随机变量，且$X \sim N(0,1), Y \sim \chi^2(n)$，则称
$$\displaystyle t = \cfrac X{\sqrt{Y/n}}$$
为自由度为$n$的t分布，记为$t(n)$
性质:
1. $\lim _{n \to +\infty} t(n) = N(0,1)$
### F分布
设$X, Y$是相互独立的随机变量，且$X \sim \chi^2(n_1), Y \sim \chi^2(n_2)$，则称
$$\displaystyle F = \cfrac {X/n_1}{Y/n_2}$$
为自由度为$n_1, n_2$的F分布，记为$F(n_1, n_2)$
性质:
1. $F\sim F(n_1,n_2),\ \cfrac {1}{F} \sim F(n_2,n_1)$

设总体均值为$\mu$，总体方差为$\sigma^2$，样本均值为$\bar{X}$，样本方差为$S^2$，则有
$$E(\bar{X}) = \mu,\ D(\bar{X}) = \cfrac {\sigma^2}{n},\ E(S^2) = \sigma^2$$
设$X_1, X_2, \cdots, X_n$是相互独立的随机变量，且$X_i \sim N(\mu,\sigma^2)$，则
 - $\bar{X}$，$S^2$相互独立
 - $\overline{X} \sim N(\mu, \cfrac {\sigma^2}n) \to U = \cfrac {\overline{X} - \mu}{\sigma / \sqrt{n}} \sim N(0, 1)$
 - $\cfrac{(n-1)S^2}{\sigma^2} \sim \chi^2(n-1)$
 - $\cfrac{\bar{X} - \mu}{S/\sqrt{n}} \sim t(n-1)$

设$X_1, X_2, \cdots, X_n$与$Y_1, Y_2, \cdots, Y_n$是相互独立的随机变量，且$X_i \sim N(\mu_1,\sigma_1^2), Y_i \sim N(\mu_2,\sigma_2^2)$，则
 - $F = \cfrac {S_1^2 / \sigma_1^2}{S_2^2 / \sigma_2^2} \sim F(n_1 - 1, n_2 - 1)$
 - 当$\sigma_1^2 = \sigma_2^2 = \sigma^2$时，$T = \cfrac {(\overline{X} - \overline{Y}) - (\mu_1 - \mu_2)}{S_\omega \sqrt{\cfrac 1{n_1} + \cfrac 1{n_2}}} \sim t(n_1 + n_2 - 2)$，其中$S_\omega^2 = \cfrac {(n_1 - 1)S_1^2 + (n_2 - 1)S_2^2}{n_1 + n_2 -2}$
# 第七章 参数估计
## 点估计
### 矩估计
$$A_l = \cfrac 1n \displaystyle \sum_{i=1}^n X_i^l \to \mu_l = E(X^l),\ l = 1, 2, \cdots, k$$
列出$k$个方程，求解得到$k$个未知数，即为$k$阶矩估计
### 最大似然估计
设$X_1, X_2, \cdots, X_n$是相互独立的随机变量，且$X_i \sim F(\theta)$，则称
$$\displaystyle L(\theta) = \prod_{i=1}^n f(x_i;\theta)$$
为似然函数，$\theta$为参数，称
$$\displaystyle \hat{\theta} = \argmax_{\theta} L(\theta)$$
为参数$\theta$的最大似然估计，通常由下式解出
$$\cfrac{\partial}{\partial\theta_i} \ln L = 0,\ i = 1,2,\cdots,k$$
## 估计量的评选标准
1. 无偏性：$\displaystyle E(\hat{\theta}) = \theta$
2. 有效性：$D(\hat{\theta_1}) \leq D(\hat{\theta_2})$，则称$\hat{\theta_1}$比$\hat{\theta_2}$更有效
3. 相合性：对于任意$\epsilon < 0$，有$\displaystyle \lim_{n \to +\infty} P\{|\hat{\theta}-\theta| < \epsilon\} = 1$
## 区间估计
一个总体：设$X \sim N(\mu,\sigma^2)$，样本容量$n$，$\overline{X}$为样本均值，$S$为样本标准差，则
$$\begin{array}{c|c} \hline \\ \text{unknown parameter} & 1-\alpha \text{ confidence interval} \\ \hline \\ \mu \ (\sigma^2 \text{ known} ) & \left( \overline{X} - u_{\frac \alpha 2} \cfrac {\sigma}{\sqrt{n}}, \overline{X} + u_{\frac \alpha 2} \cfrac {\sigma}{\sqrt{n}} \right) \\ \hline \\ \mu \ (\sigma^2 \text{ unknown}) & \left( \overline{X} - t_{\frac \alpha 2} (n-1) \cfrac S{\sqrt{n}}, \overline{X} + t_{\frac \alpha 2} (n-1) \cfrac S{\sqrt{n}} \right) \\ \hline \\ \sigma^2 & \left( \cfrac {(n-1) S^2}{\chi_{\frac {\alpha}{2}}^2 (n-1)}, \cfrac {(n-1) S^2}{\chi_{1-\frac {\alpha}{2}}^2 (n-1)} \right) \\ \hline \end{array}$$
两个总体：设$X \sim N(\mu_1,\sigma_1^2), Y \sim N(\mu_2,\sigma_2^2)$，样本容量$n_1, n_2$，$\overline{X}, \overline{Y}$为样本均值，$S_1, S_2$为样本标准差，则
$$\begin{array}{c|c} \hline \\ \text{unknown parameter} & 1-\alpha \text{ confidence interval} \\ \hline \\ \mu_1 - \mu_2 \ (\sigma_1^2, \sigma_2^2 \text{ known}) & \left( \overline{X} - \overline{Y} - u_{\frac {\alpha}2} \sqrt{\cfrac {\sigma_1^2}{n_1} + \cfrac {\sigma_2^2}{n_2}}, \overline{X} - \overline{Y} + u_{\frac {\alpha}2} \sqrt{\cfrac {\sigma_1^2}{n_1} + \cfrac {\sigma_2^2}{n_2}} \right) \\ \hline \\ {\mu_1 - \mu_2  \\ (\sigma_1^2, \sigma_2^2 \text{ unknown}，\text{but } \sigma_1^2 = \sigma_2^2)} & \left( \overline{X} - \overline{Y} - t_{\frac \alpha 2} (n_1 + n_2 - 2) S_\omega \sqrt{\cfrac 1{n_1} + \cfrac 1{n_2}}, \\ \overline{X} - \overline{Y} + t_{\frac \alpha 2} (n_1 + n_2 - 2) S_\omega \sqrt{\cfrac 1{n_1} + \cfrac 1{n_2}} \right) \\ \hline \\ \cfrac {\sigma_1^2}{\sigma_2^2} & \left( \cfrac {S_1^2}{S_2^2} \cdot \cfrac 1{F_{\frac \alpha 2}(n_1 - 1, n_2 - 2)}, \cfrac {S_1^2}{S_2^2} \cdot F_{\frac \alpha 2}(n_1 - 1, n_2 - 2) \right) \\ \hline \end{array}$$

# 第八章 假设检验
$$\begin{array}{c|c|c|c|c|c} \hline \\ \text{parameter test} & H_0 & H_1 & \text{static test} & {\text {distribution of} \\ \text{static when} \\ H_0 \text{ is true}} & \text{reject region} \\ \hline \\ \mu \ (\sigma^2 \text{ known}) & \begin{array}{c} \mu = \mu_0 \\ \mu \le \mu_0 \\ \mu \ge \mu_0 \\ \end{array} & \begin{array}{c} \mu \neq \mu_0 \\ \mu \gt \mu_0 \\ \mu \lt \mu_0 \\ \end{array} & U = \cfrac {\overline{X} - \mu_0}{\sigma / \sqrt{n}} & N(0, 1) & \begin{array}{c} |U| \ge u_{\frac \alpha 2} \\ U \ge u_\alpha \\ U \le -u_\alpha \\ \end{array} \\ \hline \\ \mu \ (\sigma^2 \text{ unknown}) & \begin{array}{c} \mu = \mu_0 \\ \mu \le \mu_0 \\ \mu \ge \mu_0 \\ \end{array} & \begin{array}{c} \mu \neq \mu_0 \\ \mu \gt \mu_0 \\ \mu \lt \mu_0 \\ \end{array} & T = \cfrac {\overline{X} - \mu_0}{S / \sqrt{n}} & t(n-1) & \begin{array}{c} |T| \ge t_{\frac \alpha 2}(n-1) \\ T \ge t_\alpha(n-1) \\ T \le -t_\alpha(n-1) \\ \end{array} \\ \hline \\ \sigma^2 \ (\mu \text{ known}) & \begin{array}{c} \sigma^2 = \sigma_0^2 \\ \sigma^2 \le \sigma_0^2 \\ \sigma^2 \ge \sigma_0^2 \\ \end{array} & \begin{array}{c} \sigma^2 \neq \sigma_0^2 \\ \sigma^2 \gt \sigma_0^2 \\ \sigma^2 \lt \sigma_0^2 \\ \end{array} & \chi^2 = \cfrac 1{\sigma_0^2} \displaystyle \sum_{i=1}^n (X_i - \mu)^2 & \chi^2(n) & \begin{array}{c} \chi^2 \le \chi_{1-\frac{\alpha}2}^2(n) \ or \\ \chi^2 \ge \chi_{\frac \alpha 2}^2(n) \\ \chi^2 \ge \chi_\alpha^2(n) \\ \chi^2 \le \chi_{1 - \alpha}^2(n) \\ \end{array} \\ \hline \\ \sigma^2 \ (\mu \text{ unknown}) & \begin{array}{c} \sigma^2 = \sigma_0^2 \\ \sigma^2 \le \sigma_0^2 \\ \sigma^2 \ge \sigma_0^2 \\ \end{array} & \begin{array}{c} \sigma^2 \neq \sigma_0^2 \\ \sigma^2 \gt \sigma_0^2 \\ \sigma^2 \lt \sigma_0^2 \\ \end{array} & \chi^2 = \cfrac {(n-1)S^2}{\sigma_0^2} & \chi^2(n-1) & \begin{array}{c} \chi^2 \le \chi_{1-\frac{\alpha}2}^2(n-1) \ or \\ \chi^2 \ge \chi_{\frac \alpha 2}^2(n-1) \\ \chi^2 \ge \chi_\alpha^2(n-1) \\ \chi^2 \le \chi_{1 - \alpha}^2(n-1) \\ \end{array} \\ \hline \\ \mu_1 - \mu_2 \\ (\sigma_1^2, \sigma_2^2 \text{ known}) & \begin{array}{c} \mu_1 - \mu_2 = \mu_0 \\ \mu_1 - \mu_2 \le \mu_0 \\ \mu_1 - \mu_2 \ge \mu_0 \end{array} & \begin{array}{c} \mu_1 - \mu_2 \neq \mu_0 \\ \mu_1 - \mu_2 \gt \mu_0 \\ \mu_1 - \mu_2 \lt \mu_0 \end{array} & U = \cfrac {\overline{X} - \overline{Y} - \mu_0}{\sqrt{\cfrac {\sigma_1^2}{n_1} + \cfrac {\sigma_2^2}{n_2}}} & N(0, 1) & \begin{array}{c} |U| \ge u_{\frac \alpha 2} \\ U \ge u_\alpha \\ U \le -u_\alpha \\ \end{array} \\ \hline \\ \mu_1 - \mu_2 \\ (\sigma_1^2, \sigma_2^2 \text{ unknown} \\ \text{but } \sigma_1^2 = \sigma_2^2) & \begin{array}{c} \mu_1 - \mu_2 = \mu_0 \\ \mu_1 - \mu_2 \le \mu_0 \\ \mu_1 - \mu_2 \ge \mu_0 \end{array} & \begin{array}{c} \mu_1 - \mu_2 \neq \mu_0 \\ \mu_1 - \mu_2 \gt \mu_0 \\ \mu_1 - \mu_2 \lt \mu_0 \end{array} & T = \cfrac {\overline{X} - \overline{Y} - \mu_0}{S_\omega \sqrt{\cfrac 1{n_1} + \cfrac 1{n_2}}} & t(n_1 + n_2 - 2) & \begin{array}{c} |T| \ge t_{\frac \alpha 2}(n_1 + n_2 - 2) \\ T \ge t_\alpha(n_1 + n_2 - 2) \\ T \le -t_\alpha(n_1 + n_2 - 2) \\ \end{array} \\  \hline \\ \sigma_1^2 = \sigma_2^2 \\ (\mu_1, \mu_2 \text{ known}) & \begin{array}{c} \sigma_1^2 = \sigma_2^2 \\ \sigma_1^2 \le \sigma_2^2 \\ \sigma_1^2 \ge \sigma_2 \\ \end{array} & \begin{array}{c} \sigma_1^2 \neq \sigma_2^2 \\ \sigma_1^2 \gt \sigma_2^2 \\ \sigma_1^2 \lt \sigma_2 \\ \end{array} & F = \cfrac {n_2 \displaystyle \sum_{i=1}^{n_1} (X_i - \mu_1)^2}{n_1 \displaystyle \sum_{j = 1}^{n_2} (Y_j - \mu_2)^2} & F(n_1, n_2) & \begin{array}{c} F \le F_{1-\frac \alpha 2} (n_1, n_2) \ or \\ F \ge F_{\frac \alpha 2} (n_1, n_2) \\ F \ge F_\alpha (n_1, n_2) \\ F \le F_{1-\alpha} (n_1, n_2) \\ \end{array} \\ \hline \\  \sigma_1^2 = \sigma_2^2 \\ (\mu_1, \mu_2 \text{ unknown}) & \begin{array}{c} \sigma_1^2 = \sigma_2^2 \\ \sigma_1^2 \le \sigma_2^2 \\ \sigma_1^2 \ge \sigma_2 \\ \end{array} & \begin{array}{c} \sigma_1^2 \neq \sigma_2^2 \\ \sigma_1^2 \gt \sigma_2^2 \\ \sigma_1^2 \lt \sigma_2 \\ \end{array} & F = \cfrac {S_1^2}{S_2^2} & F(n_1 - 1, n_2 - 2) & \begin{array}{c} F \le F_{1-\frac \alpha 2} (n_1 - 1, n_2 - 1) \ or \\ F \ge F_{\frac \alpha 2} (n_1 - 1, n_2 - 1) \\ F \ge F_\alpha (n_1 - 1, n_2 - 1) \\ F \le F_{1-\alpha} (n_1 - 1, n_2 - 1) \\ \end{array} \\ \hline  \end{array}$$
