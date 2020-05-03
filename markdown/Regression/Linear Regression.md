# Linear Regression

## Linear Regression Model

A linear model makes a prediction $\hat{y}_i$ by **simply computing a weighted sum of the input $\boldsymbol{x}_i$, plus a constant $w_0$ called the _bias_ term**:

### For single samples / instances
$\hat{y}_i = f\left(\boldsymbol{x}_{i}\right)=w_{0}+\displaystyle \sum_{j}^D w_{j} x_{i, j}$

In matrix-form:
$\hat{y}_{i}=w_{0}+ \displaystyle \sum_{j=1}^{D} w_{j} x_{i, j}=\tilde{\boldsymbol{x}}_{i}^{T} \boldsymbol{w}\
$

- $\tilde{\boldsymbol{x}}_{i} = \left[\begin{array}{c}{1} \\ {x_{i}}\end{array}\right] = \left[\begin{array}{c} {1} \\ x_{i, 1} \\ \vdots \\ {x_{i, D}}\end{array}\right] \in \mathbb{R}^{D+1}$

- $\boldsymbol{w}=\left[\begin{array}{c}{w_{0}} \\ {\vdots} \\ {w_{D}}\end{array}\right] \in \mathbb{R}^{D+1}$

### On full dataset

$
\hat{\boldsymbol{y}}=\left[\begin{array}{c}{\hat{y}_{1}} \\ {\vdots} \\ {\hat{y}_{n}}\end{array}\right]=\left[\begin{array}{c}{\tilde{\boldsymbol{x}}_{1}^{T} \boldsymbol{w}} \\ {\vdots} \\ {\tilde{\boldsymbol{x}}_{n}^{T} \boldsymbol{w}}\end{array}\right] = \underbrace{\left[\begin{array}{cc}{1} & {\boldsymbol{x}_{1}^{T}} \\ {\vdots} & {\vdots} \\ {1} & {\boldsymbol{x}_{n}^{T}}\end{array}\right]}_{=: \boldsymbol{X}} \boldsymbol{w} = \boldsymbol{X} \boldsymbol{w}
$
- $\hat{\boldsymbol{y}}$: vector containing the output for each sample
- $\boldsymbol{X}$: data-matrix containing a vector of ones as the first column as bias

> $y=\underbrace{\begin{bmatrix}{\widehat y}_1\\\vdots\\{\widehat y}_n\end{bmatrix}}_{\boldsymbol\in\mathbf ℝ^{n\times1}}=\begin{bmatrix}\widehat x_1^Tw\\\vdots\\\widehat x_n^Tw\end{bmatrix}=\begin{bmatrix}1\cdot w_0+x_{1,1}\cdot w_1+\cdots+x_{1,D}\cdot w_D\\\vdots\\1\cdot w_0+x_{n,1}\cdot w_1+\cdots+x_{n,D}\cdot w_D\end{bmatrix}=\underset{=\begin{bmatrix}1&x_1^T\\\vdots&\vdots\\1&x_n^T\end{bmatrix}\\=:\boldsymbol X\in\mathbb{R}^{n\times(1+D)}}{\underbrace{\begin{bmatrix}1&x_{1,1}&\cdots&x_{1,D}\\\vdots&\vdots&\ddots&\vdots\\1&x_{n,1}&\cdots&x_{n,D}\end{bmatrix}}\cdot}\underbrace{\begin{bmatrix}w_0\\w_1\\\vdots\\w_D\end{bmatrix}}_{=:\boldsymbol w\boldsymbol\in\mathbf ℝ^{\boldsymbol(\mathbf1\boldsymbol+\mathbf D\boldsymbol)\boldsymbol\times\mathbf1}}$