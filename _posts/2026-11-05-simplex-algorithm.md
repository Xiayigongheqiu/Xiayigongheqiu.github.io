---
layout: post
title: "Simplex Algorithm"
date: 2026-11-05
last_modified_at: 2026-11-05
---

<!--more-->

## 1. 标准形

原问题：

$$
\max Z=c^Tx
\quad\text{s.t.}\quad
Ax\le b_1,\quad Ex=b_2,\quad x\ge 0
$$

引入松弛变量：

$$
s=b_1-Ax\ge 0
$$

合并为：

$$
\max Z=d^Ty
\quad\text{s.t.}\quad
My=b,\quad y\ge 0
$$

其中：

$$
y=\begin{pmatrix}x\\s\end{pmatrix},\qquad
d=\begin{pmatrix}c\\0\end{pmatrix},\qquad
M=\begin{pmatrix}A & I_{m_1}\\ E & 0\end{pmatrix},\qquad
b=\begin{pmatrix}b_1\\b_2\end{pmatrix}
$$

---

## 2. 基可行解

从 `M` 中取 `m` 个线性无关列组成基矩阵 `B`，其余列为 `N`：

$$
M=(B,N),\qquad
y=\begin{pmatrix}y_B\\y_N\end{pmatrix},\qquad
d=\begin{pmatrix}d_B\\d_N\end{pmatrix}
$$

令非基变量为零：

$$
y_N=0
$$

得基解：

$$
y_B=B^{-1}b
$$

若：

$$
y_B\ge 0
$$

则它是基可行解，目标值为：

$$
Z=d_B^T B^{-1}b
$$

---

## 3. 检验数

非基变量检验数：

$$
r_N^T=d_N^T-d_B^T B^{-1}N
$$

对第 `j` 个非基变量：

$$
r_j=d_j-d_B^T B^{-1}M_j
$$

最优判据（最大化）：

$$
r_N\le 0
\quad\Longrightarrow\quad
\text{当前解最优}
$$

---

## 4. 入基与出基

选一个满足下式的变量 `y_j` 入基：

$$
r_j>0
$$

记：

$$
\bar b=B^{-1}b,\qquad
\bar M_j=B^{-1}M_j
$$

**无界判定。** 若：

$$
\bar M_j\le 0
$$

则 `y_j` 可无限增大，目标无界，停止。

**出基判定。** 否则取最小比值：

$$
\theta=\min_{\substack{i:\bar M_{ij}>0}}
\frac{\bar b_i}{\bar M_{ij}}
$$

达到最小比值的行 `i*` 对应的基变量出基。

---

## 5. 更新基矩阵

用 `M_j` 替换 `B` 的第 `i*` 列，得到新基：

$$
B^+
$$

然后回到第 3 步，用 `B^+` 重新计算检验数。

---

## 6. 终止与结果

当所有检验数满足：

$$
r_N\le 0
$$

停止迭代。最优解与最优值为：

$$
y_B^*=B^{-1}b
$$

$$
y_N^*=0
$$

$$
Z^*=d_B^T B^{-1}b
$$

原问题最优解 `x*` 取 `y*` 的前 `n` 个分量。

---

## 7. 算法流程

$$
\text{检验数}
\to
\text{入基}
\to
\text{无界判定}
\to
\text{最小比值出基}
\to
\text{更新基}
\to
\text{检验数}
$$

循环直到所有检验数非正。

---

## 8. 退化与循环

若最小比值出现平局，可能退化甚至循环。用 Bland 规则保证终止：

- 入基选检验数为正且下标最小的变量；
- 出基选最小比值中下标最小的基变量。
