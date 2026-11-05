# <ruby>Simplex Algorithm<rt>单纯形法</rt></ruby>

标准线性规划模型：
> max Z = cᵀx<br>
> Ax≤b₁, Ex=b₂<br>
> x≥0

A∈R<sup>m₁×n</sup>，E∈R<sup>m₂×n</sup>，c∈R<sup>n</sup>，x∈R<sup>n</sup>，b₁∈R<sup>m₁</sup>，b₂∈R<sup>m₂</sup>

引入松弛变量s=b₁-Ax≥0，则Ax+s=b₁。

令y=(x,s)ᵀ，d=(c,0)ᵀ，

$$
M=\begin{pmatrix}
A & I_{m_1} \\
E & 0
\end{pmatrix}
$$

