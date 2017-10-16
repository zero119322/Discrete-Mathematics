
## 有限集

**偏序（序关系），偏序集（有序集）**

假设 R 是集合 S 的一种关系，它满足下面三个性质：
  - [O_1]（返身性）对任何 a \in S，有 aRa
  - [O_2]（反对称性）若 aRb且bRa，则 a = b
  - [O_3]（传递性）若aRb 且 bRc，则 aRc
  则称 R 为一个**偏序** 或 简称一个**序关系**。带有偏序关系 R 的集合 S 叫做一个偏序集，或简称为有限集。当我们要标明 R时，记作 (S, R)。

最常见的序关系叫 **常序**，如在实数R的子集中正整数 N 中的 “<=” 关系（读作小于等于）。由此，一个偏序关系通常记作 \precsim，即：
$$
a \precsim b
$$

读作“a 先于 b”。

类似的：
$$
a \prec b \iff a \precsim b \land a \neq b
$$
读作：“a 严格先于 b”。
$$
b \succsim a \iff a \precsim b
$$
读作：“b 后于 a”。
$$
b \succ a \iff a \prec b
$$
读作“b 严格后于 a”。

此外：
$$
\not\precsim, \not\prec, \not\succsim, \not\succ
$$
的定义是自然的。

当不产生混淆时，常用符号
$$
\leq, <, >, \geq
$$
分别替代符号：
$$
\precsim, \prec, \succ, \succsim
$$

### 对偶序

设 \precsim 为集合 S 的任何偏序，关系 \succsim，即 a 后于 b，也是 S 的偏序，叫做对偶序。
显然， a\precsim b 当且仅当 b\succsim a；因此对偶序\precsim 是 \succsim 的逆，即\precsim = \succsim^{-1}。

### 有序子集

设 A 为有限集 S 的一个子集，假设 a, b \in A。在 A 中定义 a\precsim b 当且仅当在 S 中有 a\precsim b。
A 的这个偏序叫 A 上的**诱导序**，带有诱导序的子集 A 被称为 S 的**有序子集**。
除非特殊说明，序集 S 的任何子集被认为是 S 的有序子集。

### 半序

设定 \prec 是集合S上的一种关系，满足下面两个性质：
  - [Q_1]（非返身性） 对任何 a \in A，有 a\not\prec a;
  - [Q_2]（传递性） 若 a\prec b 且 b\prec c，则a\prec c;
  那么，\prec 叫作 S 的半序。

偏序和半序有着紧密的联系，特别地，如果 \precsim 是集合S上的偏序，则 a \prec b 意为 a \precsim b 且 a\neq b，即\prec是S上的半序。反之，如果\prec 是 S 上的半序，则 a \precsim b 意为 a\prec b 或 a = b，即 \precsim 是 S 上的偏序。

### 可比较性，线性序集

假设 a 和 b 是偏序集合 S 的元素，我们说 a 和 b 是可比较的，如果有：
$$
a \precsim b \lor b \succsim a
$$
即，一个先于另一个。否则，a 和 b 是不可比较的，记作：
$$
a \| b
$$
即，既没有 a \precsim b 也没有 b \succsim a。

“偏”是用来定义偏序集 S，因为 S 的某些元素是不需要可比较的。换句话说，假设 S 的每一对元素都是可比较的，则 S 被称为 **全序** 或 **线性序**，且 S 被叫做一条链。尽管序集 S 可能不是线性序集，S的子集A仍有可能是线性序集。很明显，线性序集 S 的每一个子集一定是线性序。

### 积集和积序

有很多方法定义所给定有序集的笛卡尔积上的序关系，下面是其中的两个方法：

  1. **积序**
     设 S 和 T 是有序集，那么下面是积集 S\times T 上的一种有序关系，称为积序：
     $$
     (a, b) \precsim (a', b'), a\precsim a' \land b \precsim b'
     $$

  2. **字典排序**
     设 S 和 T 是线性序集，那么下面积集 S \times T 上的一种序关系，称为**字典排序**。
     $$
     (a, b) \precsim (a', b'), a\prec a' \lor (a = a' \land b \precsim b')
     $$

     这个序能推广到 S_1 \times S_2 \times \cdots \times \S_n 上：
     $$
     (a_1, a_2, \cdots, a_n) \prec (a_1', a_2', \cdots, a_n')
     $$
     对于 i = 1, 2, ..., k - 1 有 a_i = a_{i}' 且 a_k < a_k'。

### Kleene闭包与序

设 A（非空）是一个线性序字母表，回顾A^* ，称作 A 的Kleene闭包，由A中所有字符串w构成，|w| 表示 w 的长度，因此下面是 A^* 上的两个序关系。
  1. **字母排序**
     - \lambda < w，\lambda是空字符串，w 是任何非空字符串；
     - 设 u = au' 和 v = bv' 是不同的字符串，a,b \in A, u', v' \in A^*，那么：
       $$
       u \prec v \iff a \prec b \lor (a = b \land u' \prec v')
       $$
  2. **长度-字母序**
     这里 A^* 先按长度排，再按字母涛掉，即对A* 中任何不同字符串u，v
     $$
     u \prec v \iff |u| < |v| \lor (|u| = |v| \land \text{alphabetical-ordered}, u \prec v)
     $$
     这个序也称作 **自由半群序**。

## 偏序集的 Hasse图

**直接前元，直接继承**

设 S 是一个偏序集，且a，b属于 S。如果 a < b，且在 S 中没有元素介于a 与 b 之间，即不存在 c \in S，使得 a < c < b，则称 a 是 b 的一个直接前元，或 b 是 a 的一个直接继元，或 b 盖住 a，记作：
$$
a \ll b
$$

假定 S 是有限偏序集，如果我们知道 S 中所有 a \ll b 的元素对 (a, b)，则知道 S 上的\ll 关系，S 中的序将完全清楚。
因为：x < y 当且仅当 x \ll y 或 在S中存在元素 a_1, a_2, ..., a_m，使得：
$$
x \ll a_1 \ll a_2 \ll \cdots a_m \ll y
$$

**Hasse图**
Hasse图是有序偏序集 S 的直接图解，它的顶点是 S 的元素，当 a << b时，从a 到 b 有一个有向边。（此时，将 b 置于高于 a 的地方,然后画一条线将它们连起来；即，向上运动引起后元）。
因此， 在图中，从点x 到 y 有一有向路，当且仅当 x < y。同样，在S的图中没有环，没有序关系是反对称的。

### 极大元素，极小元素，最小元素和最大元素

设 S 为一个偏序集，a 为 S 中的一个元素，

**极小元素**：如果 S 中没有其他元素严格先于 a。
**极大元素**：如果 S 中没有其他元素严格后于 a。

（S 中可以有多于一个极小元素和极大元素；如果 S 是无限的，那么 S 可能没有极小或极大元素，即，如果 S 是有限的，那么 S 一定至少有一个极小元素和一个极大元素）

**最小元素**：如果对于 S 中的每一个元素 x，有
$$
a \precsim x
$$
即 a 先于 S 中其他每一个元素。

**最大元素**：如果对于 S 中的每一个元素 x，有
$$
a \succsim x
$$
即 a 后于 S 中其他每一个元素。

（S 至多有一个最小元素，它一定是极小元素；S 中至多有一个最大元素，它一定是极大元素。总的说来，甚至在 S 是有限时，S 可能既无最小元素，也无最大元素。例如当 S 中的存在多个极小元素或极大元素当且相互之间不可比较时。）