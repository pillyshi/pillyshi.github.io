---
layout: post
title:  "Work diary 2020/09/26"
categories: 
---

## Theory

Currently, I'm reading Appendix B of the book "understanding machine learning". 

### Notations

- $(\Omega, \mathcal{F}, P)$: probability space
- $(\mathcal{X}, \mathcal{F}_{\mathcal{X}})$: measurable space
- $X: \Omega \rightarrow \mathbb{R}_+$: random variable
- $(\mathbb{R}\_{+}, \mathcal{B}(\mathbb{R}_{+}), l)$: measure space ($\mathcal{B}(\mathbb{R}\_{+})$ is Borel algebra and $l$ is Lebesgue measure.
- $P_X = P \circ X^{-1}$

### Marcov's inequality

$x \in \mathbb{R}_+$ can be written as follows:

$$
\begin{aligned}
x = \int_{\mathbb{R}_+} \bm{1}_{(0, x]}(z) dl.
\end{aligned}
$$

Using this property, and according to Fubini's theorem, we can say the following fact:

$$
\begin{aligned}
X(\omega) &= \int_{\mathbb{R}_+} \bm{1}_{(0, X(\omega)]}(z) dl, \\
\mathbb{E}_{P}[X] &= \int_{\Omega} \left\{\int_{\mathbb{R}_+} \bm{1}_{(0, X(\omega)]}(z) dl\right\} dP \\
&= \int_{\mathbb{R}_+} \left\{\int_{\Omega} \bm{1}_{(0, X(\omega)]}(z) dP \right\} dl \\
&= \int_{\mathbb{R}_+} P(\{\omega \in \Omega | X(\omega) \geq z\}) dl
\end{aligned}
$$

I need to check whether we can apply Fubini's theorem or not, but here I skip that steps. 

Next, I derive the lower bound of $\mathbb{E}_P[X]$ as follows: 

$$
\begin{aligned}
\forall a \in \mathbb{R}_+ : \mathbb{E}_P[X] &\geq \int_{\mathbb{R}_+} P(\{\omega \in \Omega | X(\omega) \geq z\}) \bm{1}_{(0, a]} (z) dl \\
&\geq \int_{\mathbb{R}_+} P(\{\omega \in \Omega | X(\omega) \geq a\}) \bm{1}_{(0, a]} (z) dl \\
&= P(\{\omega \in \Omega | X(\omega) \geq a\}) \int_{\mathbb{R}_+} \bm{1}_{(0, a]} (z) dl \\
&= a P(\{\omega \in \Omega | X(\omega) \geq a\}).
\end{aligned}
$$

This yields Marcov's inequality:

$$
\begin{aligned}
\forall a \in \mathbb{R}_+ : P(\{\omega \in \Omega | X(\omega) \geq a\}) \leq \frac{\mathbb{E}_P [X]}{a}.
\end{aligned}
$$

## Development
### electron-vue

- [https://qiita.com/paragaki/items/e7d3a43b50233af96424](https://https://qiita.com/paragaki/items/e7d3a43b50233af96424)


```
$ vue create mlbase-desktop


Vue CLI v4.5.6
? Please pick a preset: Manually select features
? Check the features needed for your project: Choose Vue version, Babel, TS, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with 3.x (Preview)
? Use class-style component syntax? Yes
? Use Babel alongside TypeScript (required for modern mode, auto-detected polyfills, transpiling JSX)? Yes
? Use history mode for router? (Requires proper server setup for index fallback in production) No
? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): Sass/SCSS (with node-sass)
? Pick a linter / formatter config: Basic
? Pick additional lint features: Lint on save
? Where do you prefer placing config for Babel, ESLint, etc.? In dedicated config files
? Save this as a preset for future projects? Yes
? Save preset as: mlbase
```

```
$ vue add electron-builder
$ cd <project_name>
$ yarn electron:serve
```

## Paper reading
### On the Difficulty of Evaluating Baselines

- <a href="https://arxiv.org/pdf/1905.01395v1.pdf" target="_blank">On the Difficulty of Evaluating Baselines</a>


