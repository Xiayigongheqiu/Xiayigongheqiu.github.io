---
layout: post
title: "Linear subspace"
date: 2026-09-23
last_modified_at: 2026-09-23
---

<!--more-->

```mermaid
graph LR
    %% 左侧：R^n 输入空间
    subgraph Rn [R^n 输入空间]
        direction TB
        
        subgraph RowSpace [A 的行空间 dim r]
            direction TB
            xr((x_r))
        end
        
        subgraph NullSpace [零空间 dim n-r]
            direction TB
            xn((x_n))
        end
        
        %% 空间正交关系
        RowSpace -.->|正交| NullSpace
    end

    %% 表示解的合成 x = x_r + x_n
    x((x = x_r + x_n))
    
    %% 虚线表示向量的分解与合成
    xr -.->|x_r| x
    xn -.->|x_n| x

    %% 右侧：R^m 输出空间
    subgraph Rm [R^m 输出空间]
        direction TB
        
        subgraph ColSpace [A 的列空间 dim r]
            direction TB
            b((b))
        end
        
        subgraph LeftNull [左零空间 dim m-r]
            direction TB
            zero((0))
        end
        
        %% 空间正交关系
        ColSpace -.->|正交| LeftNull
    end

    %% 矩阵 A 的映射箭头
    xr -->|Ax_r = b| b
    x -->|Ax = b| b
    xn -->|Ax_n = 0| zero
```
---
E.g.

$$
A=\begin{pmatrix}
1 & 1 & 4 \\
5 & 1 & 4
\end{pmatrix}
$$
$$
U=\begin{pmatrix}
1 & 1 & 4 \\
0 & -4 & -16
\end{pmatrix}
$$
$$
RREF=\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 4
\end{pmatrix}
$$

### C(A<sup>T</sup>)
取RREF的非零行，即C(A<sup>T</sup>)=(1,0,0)<sup>T</sup>,(0,1,4)<sup>T</sup>，dim C(A<sup>T</sup>)=r(A)=2。<br>
### N(A)
解Rx=0，取自由变量的向量，即<br>

$$
Rx=\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 4
\end{pmatrix}
\begin{pmatrix}
x_1 \\
x_2 \\
x_3
\end{pmatrix}=0
$$

解得

$$
x=x_3\begin{pmatrix}
0 \\
-4 \\
1
\end{pmatrix}
$$

即N(A)=(0,-4,1)<sup>T</sup>，dim N(A)=1。<br>
### C(A)
取A中与RREF主元列相同的列，即<br>
C(A)=(1,5)<sup>T</sup>,(1,1)<sup>T</sup>，dim C(A)=2。<br>
### N(A<sup>T</sup>)
解A<sup>T</sup>y=0，取自由变量的向量，即<br>

$$
A^Ty=\begin{pmatrix}
1 & 5 \\
1 & 1 \\
4 & 4
\end{pmatrix}
\begin{pmatrix}
y_1 \\
y_2
\end{pmatrix}=0
$$

$$
R'y=\begin{pmatrix}
1 & 0 \\
0 & 1 \\
0 & 0
\end{pmatrix}
\begin{pmatrix}
y_1 \\
y_2
\end{pmatrix}=0
$$

解得y_1=y_2=0，即N(A<sup>T</sup>)=(0,0)<sup>T</sup>，dim N(A<sup>T</sup>)=0。
