# 板书原文转录（三张照片）

> 用于校对 `四元数与欧拉角的转换.md`。照片顺序按文件名 `1.jpg` → `2.jpg` → `3.jpg`。
> 转录由图像识别得到，个别手写符号可能有误读，**数学上有歧义处以正文推导为准**。

---

## 1.jpg

**一、性质**
**二、与 3D 旋转**
（旁边有 $3 = 1^2+1^2+1^2$、$21 = 1+2^2+4^2$、$3\times21 = 63$ 之类的算术草稿）
**三、与欧拉角转换**

**① 复数：** $a + bi \quad (a,b\in\mathbb{R})$
$1\cdot i\cdot i = -1$
$i^2 = j^2 = -1$
$ij = ?$
 - ① 实数：$ij = 1$
 - ② 设 $ij = a + bi + cj$
   $q\cdot j = a + bi + cj$
   $-j = ai - b + cij = ai - b + ac + bai + cj$
   $\Rightarrow c = -1$
 - ③ $ij = k$

**② 四元数**
$q = a + bi + cj + dk \quad (a,b,c,d\in\mathbb{R})$
$i^2 = j^2 = k^2 = ijk = -1$
向量：$q = \begin{pmatrix} a \\ b \\ c \\ d \end{pmatrix}$
$q = [a, \vec{v}],\quad \vec{v} = \begin{pmatrix} b \\ c \\ d \end{pmatrix}$

**③ 模长：** $\|q\| = \sqrt{a^2+b^2+c^2+d^2} = \sqrt{a^2 + \|\vec{v}\|^2}$

加减法：$q_1 \pm q_2 = [s \pm t,\ \vec{v}_1 \pm \vec{u}]$

标量乘法：$s q = q s = sa + sb\,i + sc\,j + sd\,k$

---

## 2.jpg

**① 四元数乘法**
$jk = i,\ ki = j,\ ij = k$；$ji = -k,\ ik = -j$
$q_1 = a+bi+cj+dk$，$q_2 = e+fi+gj+hk$

$$
\begin{aligned}
q_1q_2 &= (a+bi+cj+dk)(e+fi+gj+hk)\\
&= (ae-bf-cg-dh) + (be+af-dg+ch)i \\
&\quad + (ce+df+ag-bh)j + (de-cf+bg+ah)k
\end{aligned}
$$

$$
= \begin{pmatrix}
 a & -b & -c & -d \\
 b &  a &  ? &  ? \\
 c &  ? &  a &  ? \\
 d &  ? &  ? &  a
\end{pmatrix}
\begin{pmatrix} e \\ f \\ g \\ h \end{pmatrix}
\quad(\text{板书写成矩阵}\times\text{列向量}\to q_2\text{ 的形式})
$$

设 $q_1 = (a,\vec{v}),\ \vec{v}=(b,c,d)$；$q_2 = (e,\vec{u}),\ \vec{u}=(f,g,h)$

点乘：$\vec{v}\cdot\vec{u} = bf+cg+dh$

叉乘：$\vec{v}\times\vec{u} =
\begin{vmatrix} i & j & k\\ b&c&d\\ f&g&h\end{vmatrix}
= (ch-dg)i - (bh-df)j + (bg-cf)k$

实部：$ae - \vec{v}\cdot\vec{u}$
虚部：$e\vec{v} + a\vec{u} + \vec{v}\times\vec{u}$

$$q_1q_2 = \big[ae - \vec{v}\cdot\vec{u},\ a\vec{u} + e\vec{v} + \vec{v}\times\vec{u}\big]\qquad\cdots(1)\ \text{格拉斯曼积}$$

**② 纯四元数（实部为 0，即 $a=e=0$）**
$$q_1q_2 = \big[-\vec{v}\cdot\vec{u},\ \vec{v}\times\vec{u}\big]\qquad\cdots(2)$$

**③ 逆和共轭**
$q q^{-1} = 1 \quad (q\ne 0)$
$q q^{-1} = q^{*}q = 1 \quad (q\ne 0)\qquad\cdots(3)$

---

## 3.jpg

**共轭：** $a+bi \to a - bi$
**乘：** $a^2 + b^2$
**对 $q$：** $q^{*}q = q^{*}(q) \Rightarrow \|q\|^2$
$(q^{*})^{*} = q$
$q q^{-1} = 1$
$q^{*}(q q^{-1}) = q^{*}$
$\|q\|^2 q^{-1} = q^{*}$

**模长公式（拉格朗日四平方恒等式）**
$$
\begin{aligned}
&(a_1^2+a_2^2+a_3^2+a_4^2)(b_1^2+b_2^2+b_3^2+b_4^2)\\
=\;&(a_1b_1-a_2b_2-a_3b_3-a_4b_4)^2\\
&+(a_1b_2+a_2b_1+a_3b_4-a_4b_3)^2\\
&+(a_1b_3-a_2b_4+a_3b_1+a_4b_2)^2\\
&+(a_1b_4+a_2b_3-a_3b_2-a_4b_1)^2
\end{aligned}
$$

$$\therefore\ q^{-1} = \frac{q^{*}}{\|q\|^2}\qquad\cdots(4)$$

若 $\|q\| = 1$，$q$ 是一个**单位四元数**，则 $q^{-1} = q^{*}$

**共轭** $q^{*} = a - bi - cj - dk = [a, -\vec{v}]$

$$
\begin{aligned}
q q^{*} &= [a,\vec{v}]\cdot[a,-\vec{v}]\\
&= \big[a^2 - \vec{v}\cdot(-\vec{v}),\ a(-\vec{v}) + a\vec{v} + \vec{v}\times(-\vec{v})\big]\\
&= [a^2 + \vec{v}\cdot\vec{v},\ 0] = a^2+b^2+c^2+d^2 = \|q\|^2
\end{aligned}
$$

$(q^{*})^{*} = q$
