---
layout: post
title: "Eigenvalues and eigenvectors"
date: 2026-10-01
last_modified_at: 2026-10-01
---

<!--more-->

**Ax=b　<mark>Ax=λx</mark>**

## Ax=λx

对于方程(A-λI)x=0：
- 向量x在N(A-λI)中
- 选取数λ使(A-λI)具有零空间N(A-λI)
- (A-λI)必须是奇异的，即det(A-λI)=0

E.g.

$$
(A-λI)=
\begin{pmatrix}
4-λ & -5 \\
2 & -3-λ
\end{pmatrix}
$$

|A-λI|=λ²-λ-2<br>
特征值：λ₁=-1，λ₂=2

将λ₁=-1代入(A-λ₁I)x=0，得

$$
(A-λ₁I)x₁=\begin{pmatrix}
5 & -5 \\
2 & -2
\end{pmatrix}
\begin{pmatrix}
y \\
z
\end{pmatrix}
=\begin{pmatrix}
0 \\
0
\end{pmatrix}
$$

对应于λ₁=-1的特征向量x₁=(1,1)ᵀ

将λ₂=2代入(A-λ₂I)x₂=0，得

$$
(A-λ₂I)x₂=\begin{pmatrix}
2 & -5 \\
2 & -5
\end{pmatrix}
\begin{pmatrix}
y \\
z
\end{pmatrix}
=\begin{pmatrix}
0 \\
0
\end{pmatrix}
$$

对应于λ₂=2的特征向量x₂=(5,2)ᵀ

总结：
- 计算det(A-λI)
- 求根（根即为A的特征值）
- 对于每个特征值，求解方程(A-λI)x=0

补充：
- ∑λᵢ=tr(A)
- ∏λᵢ=det(A)

---

## 矩阵的对角化

若α<sub>1</sub>、α<sub>2</sub>……α<sub>n</sub>为方阵A的n个线性无关的特征向量，则S=(α<sub>1</sub>,α<sub>2</sub>...α<sub>n</sub>)为特征向量矩阵，且S<sup>-1</sup>AS=Λ，Λ为特征值矩阵（对角矩阵），其主元分别别为对应α<sub>1</sub>、α<sub>2</sub>……α<sub>n</sub>特征向量的特征值λ<sub>1</sub>、λ<sub>2</sub>……λ<sub>n</sub>。<br>
- AS=SΛ　S<sup>-1</sup>AS=Λ　A=SΛS<sup>-1</sup>
- 若线性无关的特征向量的个数小于A的阶数，则A不能对角化
- 若A的特征值皆为0则A不可逆
- 对于相异特征值λ<sub>1</sub>、λ<sub>2</sub>……λ<sub>n</sub>的特征向量α<sub>1</sub>、α<sub>2</sub>……α<sub>n</sub>一定线性无关
- Λ<sup>k</sup>=S<sup>-1</sup>A<sup>k</sup>S；A<sup>k</sup>=SΛ<sup>k</sup>S<sup>-1</sup>
- 若存在可逆矩阵M，使B=M<sup>-1</sup>AM，则A～B
- 若A为n阶实对称矩阵（A=Aᵀ），则存在正交矩阵Q（由A的单位正交特征向量构成），使QᵀAQ=Λ
