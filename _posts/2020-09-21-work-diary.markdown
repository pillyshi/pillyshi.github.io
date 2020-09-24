---
layout: post
title:  "Work diary 2020/09/21"
categories: 
---

## 開集合

$(X, d)$を距離空間とする．
$x_0 \in X, \epsilon > 0$に対して，$B_\epsilon(x_0) = \left\\{x \in X | d(x, x_0) < \epsilon\right\\}$と定義する．いわゆる$\epsilon$-Ball．
$U \subset X$が開集合とは，任意の$x \in U$に対して，$B_\epsilon(x) \subset U$なる$\epsilon > 0$が存在することをいう．
この性質って何が嬉しいのだろう？

## 極限

極限って演算子みたいだけど，実際は述語．

### 数列の極限

$X = \\{x_n\\}_{n \in \mathbb{N}} \rightarrow a \ (n \rightarrow \infty)$

$\forall \epsilon > 0, \exists N \in \mathbb{N}: n \geq N \Rightarrow d(x_n, a) < \epsilon$

$U_N = \\{x_n \in X \| n \geq N\\}$と定義しよう．

$\epsilon$-Ball使って書くと，

$\forall \epsilon > 0, \exists N \in \mathbb{N}: B_\epsilon(a) = \left\\{x \in U_N \| d(x, a) < \epsilon\right\\} \neq \emptyset$

もう少し柔らかく書こう．

$x \in X$に対して，いくらでも近傍を取れる．
$x$の近くを調べたいのだけど，

### 関数の極限

$\lim_{x \rightarrow a} f(x) = l$

$\forall \epsilon > 0, \exists \delta > 0: d(x, a) < \delta \Rightarrow d'(f(x), l) < \epsilon$

### 関数列の極限

## 日常的な極限

## 人間の「迷い」の解析

$m$個の選択肢をユーザに提示して，ユーザは絶対に一つ選択しなければならないとする．
この時の選択にかかった時間を$t$とし，選択したものを$x \in \\{1, \ldots, m\\}$とする．
これを，$n$人のユーザにやってもらって集めたデータを，$\left\\{(t_i, x_i)\right\\}_{i=1}^n$とする．
この時，最も適切な選択肢はどれだろう？

## 改善

とある数値をモニタリングしている．
時刻$t$においてある施策を行って，数値が

## 継続率

