---
title: "#证明# 无向完全图中生成树个数"
date: 2018-09-07 23:15:08
tags: [证明, 数学, 学术]
---

使用两次计数（[double counting](https://en.wikipedia.org/wiki/Double_counting_(proof_technique))）的方法证明Caley公式。

<!--more-->

无向完全图中有`$\binom{n}{2}$`条边，其中使用`$n-1$`条边连接所有`$n$`个点的子图就是生成树。现在要证明如下命题：

{{< box >}} 无向完全图`$K_n$`中，生成树的个数`$T(n)$`为`$n^{n-2}$`。{{< /box >}}

这是Caley公式的一种等价的说法，可以使用使用两次计数（[double counting](https://en.wikipedia.org/wiki/Double_counting_(proof_technique))）的证明技巧来做。两次计数就是对同一个量用两种不同的方法计数，一种方法容易一些，另一种方法包含了待求量。因为二者相等，所以就用简单的方法求出了未知量。

第一次计数：首先设生成树个数为`$T(n)$`，则每棵树可以有`$n!$`种不同的将节点添加进这些树的顺序。换句话说就是我们可以把这些树当成是无根的（unrooted），每棵树可以从任意一个节点开始添加，而且不一定沿着边遍历，这与排列`$n$`个点没有任何区别。所以第一次计数的结果就是`$T(n)n!$`。

第二次计数：直接构造树，虽然有重复，但这样就可以方便地求出不含未知量的值。构造过程就是以一定的顺序添加边来连接节点，这会构成一系列的（有根）子树。一开始会有`$n$`棵子树，还剩下`$n-1$`条边，每添加一条边就会减少一棵子树。假设已经还剩`$k$`棵子树，则已经用了`$n-k$`条边。现在选定任何一个节点`$v$`，将**其他**的任意一棵子树挂到`$v$`下面，完成这一步操作。所以这一步的选择有`$n(k-1)$`种。把每一步连起来，则总共有

<div>$$\prod_{k=2}^n n(k-1) = n^{n-1}(n-1)! $$</div>

因为两次计数相等，所以有

<div>$$\begin{aligned}
T(n)\cdot n! & = n^{n-1}(n-1)! \\
T(n) & = n^{n-2}
\end{aligned}$$</div>

## 参考链接
1. [Wiki: Double counting (proof technique)](https://en.wikipedia.org/wiki/Double_counting_(proof_technique))
