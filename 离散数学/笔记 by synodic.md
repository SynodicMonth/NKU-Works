> 本笔记适用于对课上内容已有了解，但时间太久忘了（指考试前）的情况下复习用，不能作为初次学习的指导
> 本笔记基于《离散数学》任明明版ppt
# 第一章 命题逻辑
## 基本概念
|$p$|$q$|$\neg p$|$p\land q$|$p\lor q$|$p\to q$|$p\leftrightarrow q$|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|0|0|1|0|0|1|1|
|0|1|1|0|1|1|0|
|1|0|0|0|1|0|0|
|1|1|0|1|1|1|1|
运算优先级：$\neg > \land > \lor > \to > \leftrightarrow $
含$n$个命题变元的公式共有$2^n$个不同的赋值，真值表有$2^n$行
 - 若$A$在它的各种赋值下取值均为真，则称$A$为**重言式（永真式）**
 - 若$A$在它的各种赋值下取值均为假，则称$A$为**矛盾式（永假式）**，
 - 若$A$不是矛盾式，则称$A$为**可满足式**
## 等值演算
若$A\leftrightarrow B$为重言式，则称$A$与$B$等值，记作$A \Leftrightarrow B$
基本等值式：
1. 双重否定律$A \Leftrightarrow \neg \neg A$
2. 幂等律$A \Leftrightarrow A \land A, A \Leftrightarrow A \lor A$
3. 交换律$A \land B \Leftrightarrow B \land A, A \lor B \Leftrightarrow B \lor A$
4. 结合律$A \land (B \land C) \Leftrightarrow (A \land B) \land C, A \lor (B \lor C) \Leftrightarrow (A \lor B) \lor C$
5. 分配律$A \land (B \lor C) \Leftrightarrow (A \land B) \lor (A \land C), A \lor (B \land C) \Leftrightarrow (A \lor B) \land (A \lor C)$
6. 德摩根律$\neg (A \land B) \Leftrightarrow \neg A \lor \neg B, \neg (A \lor B) \Leftrightarrow \neg A \land \neg B$
7. 吸收律$A \land (A \lor B) \Leftrightarrow A, A \lor (A \land B) \Leftrightarrow A$
8. 零律$A \land 0 \Leftrightarrow 0, A \lor 1 \Leftrightarrow A$
9. 同一律$A \land 1 \Leftrightarrow A, A \lor 0 \Leftrightarrow A$
10. 排中律$A \lor \neg A \Leftrightarrow 1$
11. 矛盾律$A \land \neg A \Leftrightarrow 0$
12. 蕴含等值式$A \to B \Leftrightarrow \neg A \lor B$
13. 等价等值式$A \leftrightarrow B \Leftrightarrow (A \to B) \land (B \to A)$
14. 假言易位$A \to B \Leftrightarrow \neg B \to \neg A$
15. 等价否定式$A \leftrightarrow B \Leftrightarrow \neg A \leftrightarrow \neg B$
16. 归谬论证$(A \to B) \land (A \to \neg B) \to \neg A$

**对偶等值式：** 将一个逻辑等值式的$\land$与$\lor$互换，0与1互换，即可得到对偶等值式
**置换规则：** 若$A \Leftrightarrow B$，则$\Phi(A) \Leftrightarrow \Phi(B)$
**主析取范式**的所有简单合取式都是极小项，按成真赋值的二进制编号为$m_0, m_1 \cdots m_{2^n-1}$，记作$m_i \lor m_j \lor \cdots \lor m_k$
**主合取范式**的所有简单析取式都是极大项，按成假赋值的二进制编号为$M_0, M_1 \cdots M_{2^n-1}$，记作$M_i \land M_j \land \cdots \land M_k$
$n$个命题变项一共可以产生$2^n$个极大（小）项，可以产生$C_{2^n}^0+C_{2^n}^1+\cdots+C_{2^n}^{2^n}=2^{2^n}$个主合取（析取）范式
## 命题逻辑的推理
设$S$是一个联结词集合，如果任何$n(n\ge 1)$元真值函数都可以由仅含$S$中的联结词构成的公式表示，则称$S$是**联结词全功能集**
 - $\{\neg, \land, \lor\}, \{\neg, \land\}, \{\neg, \lor\}, \{\neg, \to\}, $与非$\{\uparrow\},$或非$\{\downarrow\}$都是联结词全功能集

若$A\to B \Leftrightarrow 1$，则称$A \Rightarrow B$
基本蕴含关系
1. 化简律$A \land B \Rightarrow A, A \land B \Rightarrow B$
2. 附加律$A \Rightarrow A \lor B$
3. 假前键恒真$\neg A \Rightarrow A \to B$
4. 真后键恒真$B \Rightarrow A \to B$
5. 蕴涵等值式$\neg (A \to B) \Rightarrow A,\ \neg (A \to B) \Rightarrow \neg B$
6. 前真推后真（假言推理）$A \land (A \to B) \Rightarrow B$
7. 后假推前假（拒取式）$\neg B \land (A \to B) \Rightarrow \neg A$
8. 排除法（析取三段论）$\neg A \land (A \lor B) \Rightarrow B$
9. 传递性（假言三段论）$(A \to B) \land (B \to C) \Rightarrow (A \to C)$
10. 充分性$(A \lor B) \land (A \to C) \land (B \to C) \Rightarrow C$
11. 蕴含分配率（构造性二难）$(A \to B) \land (D \to C) \Rightarrow (A \land D) \to (B \land C)$
12. 等值传递性（等价三段论）$(A \leftrightarrow B) \land (B \leftrightarrow C) \Rightarrow (A \leftrightarrow C)$
13. 构造性二难$(A \to B) \land (\neg A \to B) \Rightarrow B$
14. 破坏性二难$(A \to B) \land (C \to D) \land (\neg B \lor \neg D) \Rightarrow (\neg A \lor \neg C)$

推理规则
 - P（前提引入）
 - T（结论）
 - CP（附加前提引入)
 - 归谬法P（结论否定作为前提引入）
# 第二章 谓词逻辑
## 谓词逻辑的基本概念
**全称量词：**$\forall x P(x)$，常与$\to$联结，如$\forall x (P(x) \to Q(x))$
**存在量词：**$\exists x P(x)$，常与$\land$联结，如$\exists x (P(x) \land Q(x))$
## 等值演算
1. 量词转换律
$\neg (\forall x) P(x) \Leftrightarrow (\exists x) \neg P(x)$
$\neg (\exists x) P(x) \Leftrightarrow (\forall x) \neg P(x)$
2. 量词辖域扩张及收缩律
$(\forall x) A(x) \lor B \Leftrightarrow (\forall x) (A(x) \lor B)$
$(\forall x) A(x) \land B \Leftrightarrow (\forall x) (A(x) \land B)$
$(\exists x) A(x) \land B \Leftrightarrow (\exists x) (A(x) \land B)$
$(\exists x) A(x) \lor B \Leftrightarrow (\exists x) (A(x) \lor B)$
$(\forall x) A(x) \to B \Leftrightarrow (\exists x) (A(x) \to B)$ 后合并变号
$(\exists x) A(x) \to B \Leftrightarrow (\forall x) (A(x) \to B)$
$A \to (\forall x) B(x) \Leftrightarrow (\forall x) (A \to B(x))$ 前合并不变
$A \to (\exists x) B(x) \Leftrightarrow (\exists x) (A \to B(x))$
3. 等值分配律
$(\forall x) (A(x) \land B(x)) \Leftrightarrow ((\forall x) A(x)) \land ((\forall x) B(x))$
$(\exists x) (A(x) \lor B(x)) \Leftrightarrow ((\exists x) A(x)) \lor ((\exists x) B(x))$
4. 蕴含分配律
$(\forall x) (A(x) \lor B(x)) \Rightarrow ((\forall x) A(x)) \lor ((\forall x) B(x))$
$(\exists x) (A(x) \land B(x)) \Rightarrow ((\exists x) A(x)) \land ((\exists x) B(x))$
5. 量词换序
$(\forall x) (\forall y) P(x,y) \Leftrightarrow (\forall y) (\forall x) P(x,y) \Rightarrow (\exists y) (\forall x) P(x,y) \Rightarrow (\forall x) (\exists y) P(x,y) \Rightarrow (\exists x) (\exists y) P(x,y) \Leftrightarrow (\exists y) (\exists x) P(x,y)$
## 推理原则
1. 全称指定原则（US）$\forall x P(x) \Rightarrow P(u)$
2. 全称推广原则（UG）$P(u) \Rightarrow \forall x P(x)$
3. 存在指定原则（ES）$\exists x P(x) \Rightarrow P(c)$
4. 存在推广原则（EG）$P(c) \Rightarrow \exists x P(x)$

 - 连续使用US可用相同变元，先用ES后用US可取相同变元。
 - 先用US后用ES取不同变元，连续使用ES取不同变元。
# 第三章 集合论
## 集合论的基本概念
省略简单概念
幂集$P(A) = \{x \mid x \subseteq A\}$，如果$|A| = n$，则$|P(A)| = 2^n$
对称差$A \oplus B = (A \cup B) - (A \cap B) = (A - B) \cup (B - A)$，符合交换律和结合律
对称差与交可分配，$A \cap (B \oplus C) = (A \cap B) \oplus (A \cap C)$
差集的德摩根律，$(A - B) \cap (A - C) = A - (B \cup C), (A - B) \cup (A - C) = A - (B \cap C)$
## 容斥原理
$$|\bar{A_1} \cap \bar{A_2} \cap \cdots \cap \bar{A_n}| = |S| - \sum_{i=1}^n{|A_i|} + \sum_{1\leq i<j \leq m}|A_i \cap A_j| - \sum_{1\leq i<j<k \leq m}|A_i \cap A_j \cap A_k| + \cdots + (-1)^n|A_1 \cap A_2 \cap \cdots \cap A_n|$$
$$|A_1 \cup A_2 \cup \cdots \cup A_n| = \sum_{i=1}^n{|A_i|} - \sum_{1\leq i<j \leq m}|A_i \cap A_j| + \sum_{1\leq i<j<k \leq m}|A_i \cap A_j \cap A_k| - \cdots + (-1)^{n-1}|A_1 \cap A_2 \cap \cdots \cap A_n|$$
## 笛卡尔积与二元关系
### 笛卡尔积
设$A, B$为集合，$A \times B = \{\langle a,b \rangle \mid a \in A, b \in B\}$，称为$A$和$B$的**笛卡尔积**，记作$A \times B$
性质：
1. $A \times \varnothing = \varnothing \times A = \varnothing$
2. 不满足交换律，$A \times B \neq B \times A$
3. 不满足结合律，$A \times (B \times C) \neq (A \times B) \times C$
4. 对并和交分别满足分配律，$A \times (B \cup C) = A \times B \cup A \times C, A \times (B \cap C) = A \times B \cap A \times C$
5. 若$|A| = n, |B| = m$，则$|A \times B| = nm$

### 二元运算
如果一个非空集合，且它的元素都是有序对，则称它为**二元关系**，空集合也是二元关系，记作$R$，如$\langle x,y \rangle \in R$，可记作$xRy$
设$A, B$为集合，$R$为$A \times B$的子集，称$R$为**从$A$到$B$的（二元）关系**，当$A = B$时称为 **$A$上的（二元）关系**
空关系$\varnothing$，全域关系$E_A = A \times A$，恒等关系$I_A = \{\langle x,x \rangle \mid x \in A\}$
$|A| = n, |A \times A| = n^2, |E_A| = n^2, |I_A| = n, A$上的关系数为$2^{n^2}$
 - **定义域**$dom(R) = \{x \mid \exists y (xRy)\}$
 - **值域**$ran(R) = \{y \mid \exists x (xRy)\}$
 - **域**$fld(R) = dom(R) \cup ran(R)$
 - **逆关系**$R^{-1} = \{\langle y,x \rangle \mid \langle x,y \rangle \in R\}$
 - **合成关系**$R \circ S = \{\langle x,z \rangle \mid \exists y (\langle x,y \rangle \in R \land \langle y,z \rangle \in S)\}$
 - **$R$在$A$上的限制**$R|_A = \{\langle x,y \rangle \mid \langle x,y \rangle \in R \land x \in A\}$
 - **$A$在$R$上的像**$R[A] = ran(R|_A)$
 - **$R$的$n$次幂**$R^0 = I_A, R^n = R \circ R^{n-1}$

定理：
1. $R = (R^{-1})^{-1}$
2. $dom(R) = ran(R^{-1}), ran(R) = dom(R^{-1})$
3. $dom(R \cup S) = dom(R) \cup dom(S), ran(R \cup S) = ran(R) \cup ran(S)$
4. $dom(R \cap S) \subseteq dom(R) \cap dom(S), ran(R \cap S) \subseteq ran(R) \cap ran(S)$
5. $(R \cup S)^{-1} = R^{-1} \cup S^{-1}, (R \cap S)^{-1} = R^{-1} \cap S^{-1}$
6. $(R - S)^{-1} = R^{-1} - S^{-1}$, $(R \subseteq S)^{-1} \Rightarrow R^{-1} \subseteq S^{-1}$
7. $R \circ S = (S \circ R)^{-1}$
8. $(F \circ G) \circ H = F \circ (G \circ H)$
9. $F \circ (G \cup H) = (F \circ G) \cup (F \circ H), F \circ (G \cap H) \subseteq (F \circ G) \cap (F \circ H)$
10. 必存在$s, t$，使得$R^s = R^t$
11. $R^m \circ R^n = R^{m+n}$
12. $(R^m)^n = R^{mn}$
### 二元关系的性质
 - 自反性，$\forall x(x \in A \rightarrow \langle x,x \rangle \in R)$
 - 反自反性，$\forall x(x \in A \rightarrow \langle x,x \rangle \notin R)$
 - 对称性，$\forall x \forall y(x,y \in A \land \langle x,y \rangle \in R \Rightarrow \langle y,x \rangle \in R)$
 - 反对称性，$\forall x \forall y(x,y \in A \land \langle x,y \rangle \in R \land \langle y,x \rangle \in R \Rightarrow x = y)$
 - 传递性，$\forall x \forall y \forall z(x,y \in A \land y,z \in A \land \langle x,y \rangle \in R \land \langle y,z \rangle \in R \Rightarrow \langle x,z \rangle \in R)$

 - $R$是自反的$\ I_A \subseteq R$
 - $R$是反自反的$\ R \cap I_A = \varnothing$
 - $R$是对称的$\ R = R^{-1}$
 - $R$是反对称的$\ R \cap R^{-1} \subseteq I_A$
 - $R$是传递的$\ R \circ R \subseteq R$

**闭包**：设$R$是$A$上的关系，$R$的自反（对称或传递）闭包记作是$A$上的关系$R'$，使得$R'$满足：
 - $R \subseteq R'$
 - $R'$是自反（对称或传递）的
 - 对$A$上任何包含$R$的自反（对称或传递）关系$S$，有$R' \subseteq S$

自反闭包记作$r(R)$，对称闭包记作$s(R)$，传递闭包记作$t(R)$
 - $r(R) = R \cup I_A$
 - $s(R) = R \cup R^{-1}$
 - $t(R) = R \cup R^2 \cup R^3 \cup \cdots$

性质：
1. 不动点定理：若$R \subseteq A \times A$，则
   $R$是自反的$\iff r(R) = R$
   $R$是对称的$\iff s(R) = R$
   $R$是传递的$\iff t(R) = R$
2. 单调性：若$R, S \subseteq A \times A$，且$R \subseteq S$，则
   $r(R) \subseteq r(S)$
   $s(R) \subseteq s(S)$
   $t(R) \subseteq t(S)$
3. 交换性：若$R \subseteq A \times A$，则
   $rs(R) = sr(R)$
   $rt(R) = tr(R)$
   $st(R) \subseteq ts(R)$
4. ||自反性|对称性|传递性|
    |:-:|:-:|:-:|:-:|
    |r(R)|:heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:|
    |s(R)|:heavy_check_mark:|:heavy_check_mark:|:x:|
    |t(R)|:heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:|

**Warshell算法**：给定一个关系矩阵$R$，
```
for k = 1 to n
    for i = 1 to n
        for j = 1 to n
            R[i][j] = R[i][j] | (R[i][k] & R[k][j])
```
### 等价关系
**等价关系：** 若$R$是$A$上的关系，且$R$是自反的、对称的和传递的，则称$R$是$A$上的等价关系。
**等价类：** 若$R$是$A$上的等价关系，$\forall x \in A,\ [x]_R = \{y \mid \langle x,y \rangle \in R\}$，则称$[x]_R$是$R$的等价类，简记为$[x]$。
**商集：** 若$R$是$A$上的等价关系，以$R$的所有等价类为元素的集合称为$A$上的$R$的商集，记作$A/R$，$A/R = \{[x]_R \mid x \in A\}$
**集合的划分：** 若$A$是一个集合，$P$的每个元素都是$A$的一个子集且不为空，且$P$中的任意两个子集都不相交，且$P$中所有元素的并等于$A$，则称$P$是$A$的一个划分。
**等价关系与划分一一对应**
若$|A| = n$，则$A$上的等价关系共有$\displaystyle \sum_{k=1}^n \begin{Bmatrix} n \\ k \end{Bmatrix}$个，其中$\begin{Bmatrix} n \\ k \end{Bmatrix}$表示$n$个不同元素恰好分为$k$个集合的方案数。
### 偏序关系
**偏序关系：** 若$R$是$A$上的关系，且$R$是自反的、反对称的和传递的，则称$R$是$A$上的偏序关系，记作$\preceq$，若$\langle x,y \rangle \in R$，则称$x \preceq y$，如小于等于关系。
**$x$与$y$可比：** 若$x \preceq y$或$y \preceq x$，则称$x$与$y$可比。
**全序关系：** 若$R$是$A$上的偏序关系，且$\forall x, y \in A,\ x \preceq y$或$y \preceq x$，则称$R$是$A$上的全序（或线序）关系。
**覆盖：** 若$R$是$A$上的偏序关系，$x, y \in A$，且$x \prec y$，且不存在$z \in A$，使得$x \prec z \prec y$，则称$x$覆盖$y$。
**偏序集：** 若$A$是一个集合，$A$和$A$上的偏序关系$\preceq$一起称为偏序集，记作$\langle A, \preceq \rangle$。
**哈斯图：** 
设$\langle A, \preceq \rangle$, $B \subseteq A$，$y \in B$,
 - 若$\forall x \in B, x \preceq y$，则称$y$是$B$的最大元
 - 若$\forall x \in B, y \preceq x$，则称$y$是$B$的最小元
 - 若$\neg \exists x \in B, x \preceq y$，则称$y$是$B$的极小元
 - 若$\neg \exists x \in B, y \preceq x$，则称$y$是$B$的极大元
 - 最元存在必唯一且是极元

设$\langle A, \preceq \rangle$, $B \subseteq A$，$y \in A$,
   - 若$\forall x \in B, x \preceq y$，则称$y$是$B$的上界
   - 若$\forall x \in B, y \preceq x$，则称$y$是$B$的下界
   - 上界中的最小元称为$B$的最小上界或上确界
   - 下界中的最大元称为$B$的最大下界或下确界
   - 集合的最小元就是下确界，最大元就是上确界，反之不然

**链：** 若$\langle A, \preceq \rangle$是一个偏序集，$B \subseteq A$，且$B$中的任意两个元素$x, y$都可比，则称$B$是$A$的一条链，$|B|$称为链的长度。
**反链：** 若$\langle A, \preceq \rangle$是一个偏序集，$B \subseteq A$，如果$\forall x, y \in B, x \neq y$，$x$与$y$都是不可比的，则称$B$是$A$的一条反链，$|B|$称为反链的长度。

### 拟序关系
**拟序关系：** 若$R$是$A$上的关系，且$R$是反自反的、传递的（蕴含反对称），则称$R$是$A$上的拟序关系，记作$\prec$。
$\preceq-I_A \rightarrow \prec$，$\prec \cup I_A \rightarrow \preceq$。

# 代数系统
## 运算
**运算性质：**
略
**幺元：**
 - 左幺元：$\exist e_l \in A, \forall x \in A, e_l \cdot x = x$
 - 右幺元：$\exist e_r \in A, \forall x \in A, x \cdot e_r = x$
 - 幺元：$\exist e \in A, \forall x \in A, e \cdot x = x = x \cdot e$
 - 存在必唯一 $e_l = e_r = e$

**零元：**
 - 左零元：$\exist \theta_l \in A, \forall x \in A, \theta_l \cdot x = \theta_l$
 - 右零元：$\exist \theta_r \in A, \forall x \in A, x \cdot \theta_r = \theta_r$
 - 零元：$\exist \theta \in A, \forall x \in A, \theta \cdot x = \theta = x \cdot \theta$
 - 存在必唯一 $0_l = 0_r = 0$

**逆元：**
 - 左逆元：$\exist x^{-1} \in A, \forall x \in A, x^{-1} \cdot x = e$
 - 右逆元：$\exist x^{-1} \in A, \forall x \in A, x \cdot x^{-1} = e$
 - 逆元：$\exist x^{-1} \in A, \forall x \in A, x^{-1} \cdot x = x \cdot x^{-1} = e$
 - 左右逆元不一定相等且不一定唯一

若$\langle A, * \rangle$是一个代数系统，$|A|>1$，且存在幺元和零元，则$\theta \neq e$
若$\langle A, * \rangle$是一个代数系统，$*$可结合，$a$关于$*$的左右逆元存在，则两者相等，且逆元唯一
若$\langle A, * \rangle$是一个代数系统，存在幺元$e$，且每个元素都有左逆元，则左右逆元相等，且逆元唯一

## 代数结构

$\langle G, * \rangle$
 - 封闭，则为**广群**
 - 加上$*$满足结合律，则为**半群**
 - 加上含有幺元，则为**独异点（幺半群）**
 - 加上可逆，则为**群**
 - 可交换的群，则为**阿贝尔群**
 - $G$是群，$\exist a \in G, \forall x \in G, x=a^n$，则为**循环群**，$a$为生成元

定理：
 1. 半群的封闭子群也是半群，称为子半群
 2. $\langle S, * \rangle$是半群，$S$为有限集，则必有$a \in S, a*a=a$（幂等元）
 3. 幺半群的运算表中任何两行、列都不同
 4. 独异点中含逆元的$a, b$有$(a^{-1})^{-1}=a$，$(a*b)^{-1}=b^{-1}*a^{-1}$
 5. $G$是群，$|G|$称为群的阶
 6. 阶数大于1的群中不存在零元
 7. 存在唯一的元素$x\in G$ ，使$a * x= b$
 8. 消去律成立：$a * b = a * c \Rightarrow b = c$
 9. 有限群的运算表中的每一行或每一列都是$G$的元素的置换
 10. 群中，除幺元$e$外，不可能有任何别的等幂元
 11. $G$中的幺元$e$必定也是子群$S$中的幺元. 且元素在子群$S$中的逆元即为在群$G$中的逆元
 12. $B \subseteq G$，$B$封闭，有限，非空，则$B$必是子群
 13. $B(\neq \varnothing) \subseteq G, \forall a, b \in B, a*b^{-1}\in B \Leftrightarrow B$是$G$的子群
 14. $G$是群，$\forall a, b \in G, (a*b)*(a*b)=(a*a)*(b*b) \Leftrightarrow G$是阿贝尔群
 15. 循环群必是阿贝尔群
 16. $G$是群，$a \in G, a^n=e, n$尽量小，则称$a$的阶为$n$
 17. 有限循环群的阶为$n$，则$G=\{a, a^2, \cdots, a^{n-1}, a^n(=e)\}$，生成元的阶等于群的阶
 18. 设$G=\langle a \rangle$是循环群：
     1.  若$G$是无限循环群，则G只有$a$和$a^{-1}$两个生成元
     2.  若$G$是n阶循环群，则$a^r$是生成元$\Leftrightarrow r$是$n$的约数
     3.  G的子群仍是循环群
     4.  若$G$是无限循环群，则$G$的子群除$\{e\}$都是无限循环群
     5.  若$G$是n阶循环群，则对$n$的每个正因子$d$，$G$的子群$\langle a^{n/d} \rangle$是$d$阶循环群
