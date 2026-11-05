---
layout: post
title: "Problems of Math Ⅲ (2022)"
date: 2026-10-13
last_modified_at: 2026-11-03
---

<!--more-->

> (21)（本题满分12分）<br>
> 已知二次型f(x₁,x₂,x₃)=3x₁²+4x₂²+3x₃²+2x₁x₃<br>
> （Ⅰ）求正交矩阵Q，使正交变换x=Qy将二次型f(x₁,x₂,x₃)化为标准型；<br>
> （Ⅱ）证明 $\min_{x \neq 0} \frac{f(x)}{x^T x} = 2$ .

（Ⅰ）

$$
f(x_1,x_2,x_3)=x^T A x,\qquad
A=\begin{pmatrix}
3 & 0 & 1 \\
0 & 4 & 0 \\
1 & 0 & 3
\end{pmatrix}
$$

$$
det(A-λI)=0=\begin{vmatrix}
3-λ & 0 & 1 \\
0 & 4-λ & 0 \\
1 & 0 & 3-λ
\end{vmatrix}
$$

$$
(3-λ)\begin{vmatrix}
4-λ & 0 \\
0 & 3-λ
\end{vmatrix}
+
\begin{vmatrix}
0 & 4-λ \\
1 & 0
\end{vmatrix}=0
$$

$$
\begin{gather}
(3-\lambda)^2(4-\lambda)-(4-\lambda)=0 \\
(4-\lambda)((3-\lambda)^2-1)=0 \\
(4-\lambda)(\lambda^2-6\lambda+8)=0 \\
\lambda_1=\lambda_2=4,\quad \lambda_3=2
\end{gather}
$$

对于λ₁=λ₂=4，代入(A-λ₁I)x=0，得：

$$
(A-λ₁I)x=\begin{pmatrix}
-1 & 0 & 1 \\
0 & 0 & 0 \\
1 & 0 & -1
\end{pmatrix}x=0
$$

$$
x=x_1\begin{pmatrix}
1 \\
0 \\
1
\end{pmatrix}+
x_2\begin{pmatrix}
0 \\
1 \\
0
\end{pmatrix}
$$

则λ₁=λ₂=4对应的两个线性无关的特征向量为v₁=(1,0,1)ᵀ、v₂=(0,1,0)ᵀ，且v₁⋅v₂=0，故v₁、v₂已正交。<br>
单位化v₁、v₂，得

$$
\frac{v_1}{\lVert v_1 \rVert}=\frac{(1,0,1)^T}{\sqrt{((1,0,1)^T)^T(1,0,1)^T}}
=\begin{pmatrix}
\frac{1}{\sqrt{2}} \\
0 \\
\frac{1}{\sqrt{2}}
\end{pmatrix}
$$

$$
\frac{v_2}{\lVert v_2 \rVert}=\frac{(0,1,0)^T}{\sqrt{((0,1,0)^T)^T(0,1,0)^T}}
=\begin{pmatrix}
0 \\
1 \\
0
\end{pmatrix}
$$

同理，解(A-λ₃I)x=0得x=x₃(1,0,-1)ᵀ，单位化后得(1/√2,0,-1/√2)ᵀ。得正交矩阵Q：

$$
Q=\begin{pmatrix}
\frac{1}{\sqrt{2}} & 0 & \frac{1}{\sqrt{2}} \\
0 & 1 & 0 \\
\frac{1}{\sqrt{2}} & 0 & -\frac{1}{\sqrt{2}}
\end{pmatrix}
$$

$$
Q^TAQ=Λ=\begin{pmatrix}
4 & 0 & 0 \\
0 & 4 & 0 \\
0 & 0 & 2
\end{pmatrix}
$$

令x=Qy，得f=xᵀAx=(Qy)ᵀA(Qy)=yᵀQᵀAQy<br>
得标准型f=λ₁y₁²+λ₂y₂²+λ₃y₃²=4y₁²+4y₂²+2y₃²。

（Ⅱ）*（🐳）*<br>

由二次型

$$
f(x_1,x_2,x_3)=3x_1^2+4x_2^2+3x_3^2+2x_1x_3
$$

写成矩阵形式：

$$
f(x)=x^T A x,\qquad
A=\begin{pmatrix}
3 & 0 & 1 \\
0 & 4 & 0 \\
1 & 0 & 3
\end{pmatrix}
$$

求 \(A\) 的特征值：

$$
\det(A-\lambda I)=\begin{vmatrix}
3-\lambda & 0 & 1 \\
0 & 4-\lambda & 0 \\
1 & 0 & 3-\lambda
\end{vmatrix}=0.
$$

因此

$$
\lambda_1=\lambda_2=4,\qquad \lambda_3=2.
$$

取对应的单位正交特征向量：

u<sub>1</sub>=1/√2(1,0,1)ᵀ，u<sub>2</sub>=(0,1,0)ᵀ，u<sub>3</sub>=1/√2(1,0,-1)ᵀ

令

$$
Q=\begin{pmatrix}
\frac{1}{\sqrt{2}} & 0 & \frac{1}{\sqrt{2}} \\
0 & 1 & 0 \\
\frac{1}{\sqrt{2}} & 0 & -\frac{1}{\sqrt{2}}
\end{pmatrix}.
$$

则 \(Q\) 是正交矩阵，且

$$
Q^T A Q=
\begin{pmatrix}
4 & 0 & 0 \\
0 & 4 & 0 \\
0 & 0 & 2
\end{pmatrix}.
$$

作正交变换

$$
x=Qy,\qquad y=\begin{pmatrix}y_1\\y_2\\y_3\end{pmatrix}.
$$

则

f(x)=xᵀAx=(Qy)ᵀA(Qy)=yᵀQᵀAQy=4y₁²+4y₂²+2y₃²，

并且

xᵀx=(Qy)^T(Qy)=yᵀQᵀQy=yᵀy=y₁²+y₂²+y₃².

因此，当x≠0时，y≠0，有

f(x)/(xᵀx)<br>
=((4y₁²+4y₂²+2y₃²)/(y₁²+y₂²+y₃²))<br>
≥((2y₁²+2y₂²+2y₃²)/(y₁²+y₂²+y₃²))=2

等号成立当且仅当

$$
y_1=0,\qquad y_2=0,\qquad y_3\neq 0.
$$

此时

$$
x=Qy=
Q\begin{pmatrix}0\\0\\y_3\end{pmatrix}
=y_3\begin{pmatrix}
\frac{1}{\sqrt{2}}\\
0\\
-\frac{1}{\sqrt{2}}
\end{pmatrix}
\neq 0.
$$

并且此时

$$
\frac{f(x)}{x^T x}=2.
$$

所以

$$
\boxed{\min_{x\neq 0}\frac{f(x)}{x^T x}=2}.
$$

---

> (18)(本题满分12分)<br>
设某产品的产量Q由资本投入量x和劳动投入量y决定，生产函数Q=12x<sup>1/2</sup>y<sup>1/6</sup>，该产品的销售单价P与产量Q的关系为P=1160-1.5Q。若单位资本投入和单位劳动投入的价格分别为6和8，求利润最大时的产量。

<ruby>TR<rt>Total Revenue</rt></ruby>=PQ

<ruby>TC<rt>Total Cost</rt></ruby>=6x+8y

<ruby>π<rt>Πλεονασμός</rt></ruby>=TR-TC

给定产量Q下求成本最小化，即：

min TC=6x+8y

s.t. Q=12x<sup>1/2</sup>y<sup>1/6</sup>

L(x,y,λ)=6x+8y+λ(Q-12x<sup>1/2</sup>y<sup>1/6</sup>)

∂L/∂x=6-6λx<sup>-1/2</sup>y<sup>1/6</sup>=0

∂L/∂y=8-2λx<sup>1/2</sup>y<sup>-5/6</sup>=0

∂L/∂λ=Q-12x<sup>1/2</sup>y<sup>1/6</sup>=0

x=4y

代入Q，得y=(Q/24)<sup>3/2</sup>

代入TC，得TC=32y=32(Q/24)<sup>3/2</sup>=((√6)/9)Q<sup>3/2</sup>

π=TR-TC=(1160-1.5Q)Q-((√6)/9)Q<sup>3/2</sup>

π'=1160-3Q-((√6)/6)Q<sup>1/2</sup>=0

Q=384
