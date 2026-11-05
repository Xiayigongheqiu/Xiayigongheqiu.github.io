---
layout: post
title: "Simplex Algorithm"
date: 2026-11-05
last_modified_at: 2026-11-05
---

<!--more-->

# <ruby>Simplex Algorithm<rt>单纯形法</rt></ruby>

标准线性规划模型：
> max Z = cᵀx<br>
> Ax≤b₁, Ex=b₂<br>
> x≥0

A∈R<sup>m₁×n</sup>，E∈R<sup>m₂×n</sup>，c∈R<sup>n</sup>，x∈R<sup>n</sup>，b₁∈R<sup>m₁</sup>，b₂∈R<sup>m₂</sup>
## ⒈化为标准型

引入松弛变量s=b₁-Ax≥0，则Ax+s=b₁。

令

$$y=\begin{pmatrix}x\\
s \end{pmatrix}$$

$$d=\begin{pmatrix}c\\
0 \end{pmatrix}$$

$$M=\begin{pmatrix} A & I_{m_1}\\
E & 0\end{pmatrix}$$

$$b=\begin{pmatrix}b_1\\
b_2 \end{pmatrix}$$

则原问题化为标准型

max Z = dᵀy<br>
s.t. My=b, y≥0

## ⒉基可行解与单纯形法矩阵表示

在M中选取m个线性无关的列组成基矩阵B∈R<sup>m×m</sup>

其余列组成非基矩阵N

将y相应分块为

$$y=\begin{pmatrix}y_B\\
y_N \end{pmatrix}$$

$$y=\begin{pmatrix} B & N \end{pmatrix}$$

$$d=\begin{pmatrix}d_B\\
d_N \end{pmatrix}$$

则约束可写为

$$B_{y_B}+N_{y_N}=b$$

令非基变量y<sub>N</sub>=0，得到基解y<sub>B</sub>=B<sup>-1</sup>b

若B<sup>-1</sup>b>0，则其为基可行解，对应目标值

$$Z=d_{B}^{T}B^{-1}b$$

非基变量检验数

$$r_{N}^{T}=d_{N}^{T}-d_{B}^{T}B^{-1}N$$

即对应第j个非基变量

$$r_j=d_j-d_{B}^{T}B^{-1}M_j$$

若r<sub>N</sub>≤0，则当前基可行解最优；若存在r<sub>j</sub>>0，则令y<sub>j</sub>入基。

## ⒊ 入基、出基与无界判定

设选中的入基变量为 \(y_j\)，对应列为 \(M_j\)。由约束

$$
B y_B+M_j y_j=b
$$

得

$$
y_B=\bar b-y_j\bar M_j,
\qquad
\bar b=B^{-1}b,
\quad
\bar M_j=B^{-1}M_j.
$$

其中 \(\bar M_{ij}\) 是 \(\bar M_j\) 的第 \(i\) 个分量，即

$$
\bar M_{ij}=(B^{-1}M_j)_i.
$$

**无界判定。** 若

$$
\bar M_j\le 0,
$$

则 \(y_j\) 可无限增大而仍保持 \(y_B\ge0\)，目标值

$$
Z=Z_0+r_jy_j
$$

无界增大，故原问题无界。

**出基判定。** 否则存在 \(\bar M_{ij}>0\)，取最大步长

$$
\theta=\min_{\substack{i:\bar M_{ij}>0}}
\frac{\bar b_i}{\bar M_{ij}},
$$

并由

$$
i^*=\arg\min_{\substack{i:\bar M_{ij}>0}}
\frac{\bar b_i}{\bar M_{ij}}
$$

确定出基行。第 \(i^*\) 个基变量出基，\(y_j\) 入基。

**更新基矩阵。** 用 \(M_j\) 替换 \(B\) 的第 \(i^*\) 列，得到新基

$$
B^+ = B \text{ 的第 } i^* \text{ 列换成 } M_j,
$$

然后回到检验数步骤，用 \(B^+\) 重新计算 \(\bar b\)、\(\bar M_j\) 与 \(r_N\)，继续迭代。
