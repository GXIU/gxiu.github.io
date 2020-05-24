---
layout: cobalt
title: Fokker-Planck方程
categories: [笔记]
---

Update: 2020/05/11

## Fokker-Planck方程

如果一个马氏过程$X_t$的转移概率密度是$\rho(x, t | y, s)$, 那么它满足一个随机微分方程
$$
\mathrm{d} X_{t}=f\left(t, X_{t}\right) \mathrm{d} t+g\left(t, X_{t}\right) \mathrm{d} B_{t}
$$
其中$B_t$是一个布朗运动。

- 离散形式：
  $$
  \Delta X_{t} =f\left(t, X_{t}\right) \Delta t+g\left(t, X_{t}\right) \Delta B_{t}
  $$
  其中$\Delta X_{t}:=X_{t+\Delta t}-X_{t} \text { and } \Delta B_{t} :=B_{t+\Delta t}-B_{t}$. 

- 计算几个量备用：
  $$
  \begin{aligned}
  \mathbb{E}\left[f\left(t, X_{t}\right) \Delta t | X_{t}=z\right] &=\mathbb{E}\left[f\left(t, X_{t}\right) | X_{t}=z\right] \Delta t=f(t, z) \Delta t \\
  \mathbb{E}\left[g\left(t, X_{t}\right) \Delta B_{t} | X_{t}=z\right] &=g(t, z) \mathbb{E}\left[\Delta B_{t} | X_{t}=z\right]=g(t, z) \mathbb{E}\left[\Delta B_{t}\right]=0 \\
  \mathbb{E}\left[g\left(t, X_{t}\right)^{2}\left(\Delta B_{t}\right)^{2} | X_{t}=z\right] &=g(t, z)^{2} \mathbb{E}\left[\left(\Delta B_{t}\right)^{2} | X_{t}=z\right] \\
  &=g(t, z)^{2} \mathbb{E}\left[\left(\Delta B_{t}\right)^{2}\right]=g(t, z)^{2} \Delta t
  \end{aligned}
  $$

  - 所以原过程的跳的条件期望为
    $$
    \begin{align}
    &\mathbb{E}\left[\Delta X_{t} | X_{t}=z\right]
    \\=&\mathbb{E}\left[f\left(t, X_{t}\right) \Delta t+g\left(t, X_{t}\right) \Delta B_{t} | X_{t}=z\right]
    \\=&f(t, z) \Delta t
    \\ =&\int(x-z) \rho(x, t+\Delta t | z, t) \mathrm{d} x
    \end{align}
    $$
    条件方差是：
    $$
    \begin{align}
    &\mathbb{E}\left[\left(\Delta X_{t}\right)^{2} | X_{t}=z\right] 
    \\=& \mathbb{E}\left[g\left(t, X_{t}\right)^{2}\left(\Delta B_{t}\right)^{2} | X_{t}=z\right] \\
    =&g(t, z)^{2} \Delta t+o(\Delta t) \\
    =&\int(x-z)^2 \rho(x, t+\Delta t | z, t) \mathrm{d} x
    \end{align}
    $$
    

- Chapman-Kolmogorov 方程
  $$
  \rho(x, t+\Delta t | y, s)=\int \rho(x, t+\Delta t | z, t) \rho(z, t | y, s) \mathrm{d} z
  $$
  再乘一个光滑函数$R(x)$再积分，得到一个均值版本的CK方程：
  $$
  \int \mathrm{d} x R(x) \rho(x, t+\Delta t | y, s)=\int \mathrm{d} x R(x) \int \rho(x, t+\Delta t | z, t) \rho(z, t | y, s) \mathrm{d} z
  $$
  对右侧$R(\cdot)$进行展开，得到
  $$
  \begin{align}&\int R(x) \rho(x, t+\Delta t | z, t) \mathrm{d} x \notag \\=&\int\left\{R(z)+R^{\prime}(z)(x-z)+\frac{1}{2} R^{\prime \prime}(z)(x-z)^{2}+\cdots\right\} \rho(x, t+\Delta t | z, t) \mathrm{d} x \notag \\=&R(z) \int \rho(x, t+\Delta t | z, t) \mathrm{d} x \notag \\&+R^{\prime}(z) \int(x-z) \rho(x, t+\Delta t | z, t) \mathrm{d} x \notag \\&+R^{\prime \prime}(z) \int(x-z)^{2} \rho(x, t+\Delta t | z, t) \mathrm{d} x \notag \\=&R(z)+R^{\prime}(z) f(t, z) \Delta t+\frac{1}{2} R^{\prime \prime}(z) g(t, z)^{2} \Delta t+o(\Delta t)\end{align}
  $$
  左侧密度按时间展开：
  $$
  \begin{align}\int R(x) \rho(x, t+\Delta t | y, s) \mathrm{d} x &=\int R(x)\left[\rho(x, t | y, s)+\partial_{t} \rho(x, t | y, s) \Delta t+o(\Delta t)\right] \mathrm{d} x \notag\\&=\int R(z) \rho(z, t | y, s) \mathrm{d} z+\Delta t \int R(z) \partial_{t} \rho(z, t | y, s) \mathrm{d} z+o(\Delta t)\end{align}
  $$
  上面两式联立，对照系数，得到
  $$
  0=\int\left\{R(z) \partial_{t} \rho(z, t | y, s)-\left[R^{\prime}(z) f(t, z)+\frac{1}{2} R^{\prime \prime}(z) g(t, z)^{2}\right] \rho(z, t | y, s)\right\} \mathrm{d} z
  $$
  将$R(\cdot)$的微分项都通过分布积分变成$R(\cdot)$: 
  $$
  0=\int R(z)\left\{\partial_{t} \rho(z, t | y, s)+\partial_{z}[f(t, z) \rho(z, t | y, s)]-\frac{1}{2} \partial_{z z}\left[g(t, z)^{2} \rho(z, t | y, s)\right]\right\} \mathrm{d} z
  $$
  因为上面的式子对于任意的测试函数$R(\cdot)$都成立，所以打括号里面一定是$0$. 所以有Fokker-Planck方程：
  $$
  \partial_{t} \rho(z, t | y, s)=\left[-\partial_{z} f(t, z)+\frac{1}{2} \partial_{z z} g(t, z)^{2}\right] \rho(z, t | y, s)
  $$
  这是转移密度的时空衰减规律的自然体现。