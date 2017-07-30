## What is Machine Learning

>A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E

Example: playing checkers.

- E = the experience of playing many games of checkers
- T = the task of playing checkers.
- P = the probability that the program will win the next game.

In general, any machine learning problem can be assigned to one of two broad classifications:
Supervised learning and Unsupervised learning.

---
### Supervised learning
> Problems where the desired output is provided for examples int the training set

- Regression : A subset of supervised learning problems where output is continuous
- Classification : A subset of supervised learining problems where output is discrete
![]( https://raw.githubusercontent.com/csJd/csJd.github.io/res/ml-pic1.png)

---
#### Linner regression

Hypothesis function: 
![][Hypothesis function]

Cost function (Squared error function):
![][Cost function]

Parameters: θ₀, θ₁
Goal: minimize cost function

Gradient Descent Algorithm:
![][GDA]

Gradient Descent for Multiple Variables:
![][GDMV]

Feature Scaling (mean normalization):
![][FS]

Learning rate α : 
>If α is too small: slow convergence
>If α is too large: J may not decrease on every iteration and thus may not converge

Normal Equation (find the optimum theta without iteration):
![][NE]

Comparison of gradient descent and the normal equation

Gradient Descent | Normal Equation
:---:|:---:
Need to choose alpha | No need to choose alpha
Needs many iterations | No need to iterate
O(kn²) | O(n³), need to calculate inverse of X'X
Works well when n is large | Slow if n is very large

---
#### Logistic regression
Logistic Function (Sigmoid Function) :
![][LRHR]

Cost function:
![][LRCF1]
![][LRCF]

---
#### Overfitting
> overfitting, or high variance, is caused by a hypothesis function that fits the available data but does not generalize well to predict new data. 

---
### Unsupervised learning 
> Problems where wo are not told what the desired output is


---
[Hypothesis function]: http://latex.codecogs.com/gif.latex?h_\theta(x)=\theta_0+\theta_1x

[Cost function]: http://latex.codecogs.com/gif.latex?J(\theta_0,\theta_1)=\frac{1}{2m}\sum_{i=1}^m(h_\theta(x_i)-y_i)^2)

[GDA]: http://latex.codecogs.com/gif.latex?\begin{align*}&%20\text{repeat%20until%20convergence:}%20\;%20\lbrace%20\newline%20\;%20&%20\theta_j%20:=%20\theta_j-\alpha\frac{\partial}{\partial\theta_j}J(\theta_0,\theta_1)\newline%20\rbrace\end{align*}

[GDMV]: http://latex.codecogs.com/gif.latex?\begin{align*}&%20\text{repeat%20until%20convergence:}%20\;%20\lbrace%20\newline%20\;%20&%20\theta_j%20:=%20\theta_j%20-%20\alpha%20\frac{1}{m}%20\sum\limits_{i=1}^{m}%20(h_\theta(x^{(i)})%20-%20y^{(i)})%20\cdot%20x_j^{(i)}%20\;%20&%20\text{for%20j%20:=%200...n}\newline%20\rbrace\end{align*}

[FS]: http://latex.codecogs.com/gif.latex?x_i:=\dfrac{x_i-\mu_i}{s_i}

[NE]: http://latex.codecogs.com/gif.latex?\theta=(X^TX)^{-1}X^Ty

[LRHR]:http://latex.codecogs.com/gif.latex?h_\theta(x)=\frac{1}{1+e^{-\theta^Tx}}

[LRCF1]:http://latex.codecogs.com/gif.latex?\begin{align*}&%20J(\theta)%20=%20\dfrac{1}{m}%20\sum_{i=1}^m%20\mathrm{Cost}(h_\theta(x^{(i)}),y^{(i)})%20\newline%20&%20\mathrm{Cost}(h_\theta(x),y)%20=%20-\log(h_\theta(x))%20\;%20&%20\text{if%20y%20=%201}%20\newline%20&%20\mathrm{Cost}(h_\theta(x),y)%20=%20-\log(1-h_\theta(x))%20\;%20&%20\text{if%20y%20=%200}\end{align*}

[LRCF]:http://latex.codecogs.com/gif.latex?J(\theta)%20=%20-%20\frac{1}{m}%20\displaystyle%20\sum_{i=1}^m%20[y^{(i)}\log%20(h_\theta%20(x^{(i)}))%20+%20(1%20-%20y^{(i)})\log%20(1%20-%20h_\theta(x^{(i)}))]
