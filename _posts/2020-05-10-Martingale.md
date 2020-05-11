---
layout: cobalt
title: 鞅论
categories: [笔记]
---

Update: 2020/05/10

## 鞅定义在$\sigma$-代数流上

- $(\Omega, \mathcal{F}, P)$是一个概率空间，$\mathcal{F}_n$是其上的子$\sigma$代数，而且$\mathcal{F}_m\subseteq\mathcal{F}_{m+1}$. 
- $\{X_n\}$是上述概率空间上的随机过程，状态空间为$(E,\mathcal{E})$, $m_n=\sigma(X_0,\dots,X_n)$称为$\{X_n\}$的自然历史。
  - $m_\infty$是使过程可测的最小$\sigma$代数。
  - adapted（适应的）：$X_n\in \mathcal{F},\forall n$

1. 如果$\mathcal{F_n}\uparrow \mathcal{F},A\in \mathcal{F}$, 那么 
   $$P(A|\mathcal{F}_n)\to 1_A, a.s., n\to\infty$$

- 鞅、上鞅、下鞅的定义（[链接](http://www.chezaiyi.cn/philosophy/228218.html)）
  - 调和函数的定义（上调和，下调和）：$u(x)\gtreqqless \frac{1}{2\pi}\inf_0^\infty u(x+re^{i\theta})d\theta$ 左边确定，右边随机，相当于$X_{n+1}$, 积分相当于期望。
  - 几个例子：
    - $X_n = E[Y|\mathcal{F_n}]$
    - 简单随机游走
    - 两个硬币一样或什么都没有
2. 琴生不等式：对于凸函数$\psi\in \mathcal{B}(\mathbb{R})$, 有
   $$\psi(\mathbb{E}(X))\le\mathbb{E}\psi(X).$$ 
   这个结论对于条件期望也成立。
   - **命题**：$X_n$是下鞅，$\psi$是递增凸函数，那么$\psi(X_n)$是下鞅；如果$X_n$是鞅，那么只需要$\psi$是凸函数，就能保证$\psi(X_n)$是下鞅。

## 下鞅分解定理

- 可测序列：$A_0 = 0$, $A_n\le A_{n+1}$
- 可料序列：$A_n\in\mathcal{F}_{n-1}$, 比停时要强。

## 停时

### 停时的定义

### 停时定理

## 一致可积，$L_1$收敛，极限定理

Durrett 4.6