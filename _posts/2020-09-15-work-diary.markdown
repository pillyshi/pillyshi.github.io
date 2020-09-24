---
layout: post
title:  "Work diary 2020/09/15"
categories: 
---

## 測度論・確率論

### 1変数の述語の話

述語$f: \mathcal{X} \rightarrow \{0, 1\}$を考える．
以下の二つは命題である．

- $\forall x \in \mathcal{X}: f(x)$
- $\exists x \in \mathcal{X}: f(x)$

以下の集合$B$を考えてみよう．

$$
\begin{aligned}
B = \left\{x \in \mathcal{X} | f(x) \right\}
\end{aligned}
$$

上記の二つの命題は，

- $B = \mathcal{X}$
- $B \neq \emptyset$

と書き換えられるだろう．

確率測度を導入すれば，もう少し柔軟な議論ができる．
確率空間$(\mathcal{X}, \mathcal{F}, P)$を用意して，$f$は$\mathcal{F}$-可測だとする．
こうすれば，最初の二つの命題を以下のように考えても良いだろう．

- $P(B) = 1$
- $P(B) \neq 0$

注意したいのは，$P$に依存しているということだ．同じ集合でも，確率測度によって成り立つとするか成り立たないとするかが変わってくる．

### 2変数の述語の話

2変数の述語$f: \mathcal{X} \times \mathcal{Y} \rightarrow \{0, 1\}$を考える．
以下の二つは述語である．

- $\forall x \in \mathcal{X}: f(x, y)$
- $\exists x \in \mathcal{X}: f(x, y)$

$y \in \mathcal{Y}$に値を入れると，これは命題となる．ここで，以下のような集合を考えてみよう．

$$
\begin{aligned}
B_f = \left\{y \in \mathcal{Y} | \exists x \in \mathcal{X}: f(x, y) \right\}
\end{aligned}
$$

存在量化子は面白い性質をもっている．この集合は以下のように書き換えられる．

$$
\begin{aligned}
B_f = \cup_{x \in \mathcal{X}} \left\{y \in \mathcal{Y} | f(x, y)\right\}
\end{aligned}
$$

ここで，確率空間$(\mathcal{Y}, \mathcal{F}, P)$を導入しよう．任意の$x \in \mathcal{X}$に対して，$f(x, \cdot)$は$\mathcal{F}$-可測だとする．
そうすると，任意の$x \in \mathcal{X}$に対して，$\left\{y \in \mathcal{Y} | f(x, y)\right\} \in \mathcal{F}$である．
さらに，$\mathcal{F}$は$\sigma$-加法族なので，$B_f \in \mathcal{F}$である．よって，$P$で測れる．

測度の劣加法性を使えば，以下のように$P(B_f)$の上界を出せる．

$$
\begin{aligned}
P(B_f) &= P(\cup_{x \in \mathcal{X}} \left\{y \in \mathcal{Y} | f(x, y)\right\}) \\
&\leq \sum_{x \in \mathcal{X}} P(\left\{y \in \mathcal{Y} | f(x, y)\right\})
\end{aligned}
$$

一方で，全称量化子の場合はどうだろう．
以下のように$B_f$を定義する．

$$
\begin{aligned}
B_f = \left\{y \in \mathcal{Y} | \forall x \in \mathcal{X}: f(x, y) \right\}
\end{aligned}
$$

ここで，$P(B_f^c) = 1 - P(B_f)$である．ただし，$B_f^c$は$B_f$の補集合を意味する．

$$
\begin{aligned}
P(B_f^c) &= P(\left\{y \in \mathcal{Y} | \exists x \in \mathcal{X} : \neg f(x, y)\right\}) \\
&= P(\cup_{x \in \mathcal{X}} \left\{y \in \mathcal{Y} | \neg f(x, y)\right\}) \\
&\leq \sum_{x \in \mathcal{X}} P(\left\{y \in \mathcal{Y} | \neg f(x, y)\right\}) =: \delta
\end{aligned}
$$

なので，

$$
\begin{aligned}
P(B_f) \geq 1 - \delta
\end{aligned}
$$

となる．存在量化子の場合は上界が，全称量化子の時は下界が出る．これはめちゃくちゃ大事．

### 実数値関数の話

実数値関数などは，不等号を使えば述語にできる．例えば，$f: \mathcal{X} \rightarrow \mathbb{R}$を考える．
以下の二つは命題である．

- $\forall x \in \mathcal{X} : f(x) \leq c$
- $\exists x \in \mathcal{X} : f(x) \leq c$

ただし，$c \in \mathbb{R}$は定数．
ここでの述語は，$g(x) = f(x) \leq c$である．
こう考えると，上記のテクニックが使える．

### あいも変わらず脱線

色々な学問的書籍ではすでに問題が提起されており，きちんと整理された状態で提示される．
実問題の場合，そんなことはほとんどない．
つまり本を読んだだけでは，ここのトレーニングがきちんとできない．

少し医学統計の本を読んでみた．
まず例題として出てきたのは，「この薬はこの病気に効くのだろうか？」というものだった．
基本的な手順は，

1. その病気の人を集める．
2. 評価指標となる数値を測定
3. 薬を投入後，評価指標となる数値を測定

というものだろうか．ここで，平均値の差の検定というものを思い出した．
平均値の差の検定については，以下に詳しく書いてある．

- [24\-3\. 2標本t検定とは \| 統計学の時間 \| 統計WEB](https://bellcurve.jp/statistics/course/9427.html)

確率空間$(\Omega, \mathcal{F}, P)$を用意する．
次に，確率変数$X_i: \Omega \rightarrow \mathbb{R} \ \forall i = 1, \ldots, m$を用意する．
そして，サンプル$S: \omega \mapsto (X_1(\omega), \ldots, X_m(\omega))$を用意する．
最後に，$f: \bm{x} \mapsto \frac{1}{m} \sum_{i=1}^m x_i$を用意する．ただし，$\bm{x} = \left[x_1 \ \cdots \ x_m \right]^T$であり，$x_i \in \mathbb{R} \ \forall i = 1, \ldots, m$である．
この時の，$f \circ S$を調べる．僕はこれを，$f$の確率変数化と呼んでいる．

さて，例題に戻ると，薬の効果は

**薬を投入した後の評価指標の値 - 薬を投入する前の評価指標の値**

で測るとして，これを$X_i$としよう．実現値は$x_i$．
ここでの帰無仮説は，「薬の効果の平均は0である」としよう．
この帰無仮説が発生する確率をp値と呼ぶが，これは，$P(\left\{\omega \in \Omega | f \circ S (\omega) = 0 \right\})$と，表すことができそうだ．
ここから何ができるだろうか？
従う分布を決めてしまえばそれはそれで何か出るのだろうけど，分布を仮定するパラメトリックな方法はあまり好きではない．
それ以外は？まだ僕には何も見えてこない．これが見えるようになると強いのだろう．


## 量子力学の話

今日から以下の本で，量子力学に入門する．

<a href="https://www.amazon.co.jp/gp/product/406153209X/ref=as_li_ss_il?ie=UTF8&psc=1&linkCode=li2&tag=nettodesyuu00-22&linkId=aad08fd381d00ad868d2c8b7e363a51d&language=ja_JP" target="_blank"><img border="0" src="//ws-fe.amazon-adsystem.com/widgets/q?_encoding=UTF8&ASIN=406153209X&Format=_SL160_&ID=AsinImage&MarketPlace=JP&ServiceVersion=20070822&WS=1&tag=nettodesyuu00-22&language=ja_JP" ></a><img src="https://ir-jp.amazon-adsystem.com/e/ir?t=nettodesyuu00-22&language=ja_JP&l=li2&o=9&a=406153209X" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />

まずは概念的なものを掴むこと．
できればプログラミングしながら学べると良い．
物理学のシミュレーションはとてもやってみたかった．
