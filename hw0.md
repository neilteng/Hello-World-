# hw0

## 1. Probability and Statistics
### 1. game-roll of a dice
If the dice is fair. This is not a good bet. Because the expatation of the payout is nagetive:
$$\mathbb{E}(payout)=\frac{1}{6}(1-\frac{1}{4}-\frac{1}{4}-\frac{1}{4}-\frac{1}{4}-\frac{1}{4})=-\frac{1}{24} $$
<div STYLE="page-break-after: always;"></div> 

### 2. CDF
$$\mathbb{C}(x)=
\begin{cases}
0& {x < 0};\\
2x^2& {0 \le x \le \frac{1}{2}};\\
\cfrac{1}{2}+4x-2x^2 \big|_{\frac{1}{2}}^1 & \frac{1}{2}< x \le 1 ;\\
1& {x>1}.
\end{cases}$$

<div STYLE="page-break-after: always;"></div> 

### 3. Variance
Denote f as the short-hand of f(x) which is the PDF of X.

$
Var[X]=\mathbb{E}[(X-\mu)^2] \\
=\int (X-\mu)^2fd(x) \\
=\int X^2 f d(x)+\int \mu^2 fd(x)-2\int X \mu f d(x)\\
=\mathbb{E}[X^2]+\mu^2 \int f d(X)-2\mu \int X f d(x)\\
=\mathbb{E}[X^2]+\mu^2-2\mu\cdot\mu \\
=\mathbb{E}[X^2]-(\mathbb{E}[X])^2
$

<div STYLE="page-break-after: always;"></div> 
 
### 4. Evaluate integral
Denote p(x) as p.

$
\because \int_{-\infty}^{+\infty}px^2dx=\mathbb{E}[X^2]=Var[X]+(\mathbb{E}[X])^2=1^2+0^2=1
$


$
\int_{-\infty}^{+\infty}p(ax^2+bx+c)dx \\
=(a\int_{-\infty}^{+\infty}px^2dx+b\int_{-\infty}^{+\infty}pxdx+c\int_{-\infty}^{+\infty}pdx)\\
=a\cdot 1+b\cdot \mu+ c \cdot 1=a+0+c=a+c
$

<div STYLE="page-break-after: always;"></div> 
 
## 2. Proving stuff
### 5. prove that ...

Set $f=ln\ x-x+1, \forall x>0$

The first derivatives of $f$ is $f'=\cfrac1x-1$;

The second derivatives of $f$ is $f''=-\cfrac{1}{x^2}$;

$\because \forall  x>0,we \ have \  f''<0;$

$\therefore f$ is convex, and we have only one maximun optimal solution when x>0, which will only be achieved at $f'=0$.

and the solution of $f'=0$ is:

 $$\cfrac1x-1=0\rightarrow x=1$$

  Since x=1 is the only solution of $f'=0$, at which 
 $$ln(1)-1+1=0 \rightarrow ln(x)=x-1 $$

 so all the other x>0 we will have f<0.

 so $\forall x>0$, ln(x)=x-1 is achieved iif x=1.

<div STYLE="page-break-after: always;"></div> 

### 6. Consider two discrete probability distributions p and q over k outcomes:

(a)

$
\sum p_ilog \frac{p_i}{q_i}=\sum -p_ilog \frac{q_i}{p_i}
$

According to Q5, we have  $log\ x \le x-1, \forall x>0 \rightarrow -log\ x \ge 1-x,\forall x>0$.

so

$
\sum -p_ilog \frac{q_i}{p_i} \ge \sum p_i(1-\frac{q_i}{p_i})=\sum p_i - \sum p_i \cdot \frac{q_i}{p_i}=\sum p_i-\sum q_i=1-1=0\\
\Rightarrow \sum p_ilog \frac{p_i}{q_i} \ge 0
$ 
with equation iif $p_i=q_i,\forall i$

(b) According to Q5, equation is avhieved at x=1. That means $p_i=q_i,\forall i$ under this circumstance.

(c) 
Assume we have two coin (1) is not fair (denote as P), (2) is fair(denote as Q). And the posibilities shown as follow:

|#| Head | Tail  |
| ---| --- | --- |
|(1)P| 1/4 | 3/4   |
|(2)Q| 1/2 | 1/2   |

so 

KL(p,q)=(1/4)*log(1/2)+(3/4)*log(3/2)=0.056810945375766

KL(q,p)=(1/2)*log(2)+(1/2)*log(2/3)=0.06246936830415

so KL(p,q) != KL(q,p).

<div STYLE="page-break-after: always;"></div> 

 ## 3. Calculus
### 7. x = (x1, x2, x3, x4, x5, x6)

1. evaluation at $\hat{X}$ = (5,−1,6,12,7,−5)
   
   $f(X)=\sigma(log(5(max \{5,-1\} \cdot \cfrac{6}{12}-(7-5)))+\cfrac12)\\
   =\sigma(log(5(5 \cdot \cfrac{6}{12}-(7-5)))+\cfrac12)\\
   =\sigma(log(5(5 \cdot \cfrac{6}{12}-(7-5)))+\cfrac12)\\
   =\sigma(log\cfrac{5}{2}+\cfrac12)\\
   =\cfrac{1}{1+e^{-(log\frac{5}{2}+\frac12)}}\\
   =\cfrac{1}{1+e^{-(log\frac{5}{2}+\frac12)}}\\
   ==\cfrac{1}{1+e^{-log\frac{5}{2}} \cdot e^{-\frac12}}\\
   =\cfrac{1}{1+\frac{2}{5} \cdot e^{-\frac12}}\\
   \approx 0.80475626151755\\
   \approx 0.805\\
   $

2. gradient ∇xf(·) and evaluate it at the same point.

    Denote $[5(max \{x_1,x_2\} \cdot \cfrac{x_3}{x_4}-(x_5-x_6))]$ as [*].

    $\forall x_i$ in $(x_1, x_2, x_3, x_4, x_5, x_6)$, we hold following equations:

    $
    \cfrac{\partial f}{\partial x_i} \\
    = -[1+e^{-\frac12} \cdot [*]^{-1}]^{-2} \ \cdot \ e^{-\frac12} \ \cdot \ \cfrac{\partial }{\partial x_i}([*]^{-1})\\
    =-\frac{1}{[1+e^{-\frac12} \cdot [*]^{-1}]^{2}} \ \cdot \ e^{-\frac12} \ \cdot \ (-1) \ \cdot \ [*]^{-2} \ \cdot \  \cfrac{\partial [*]}{\partial x_i}\\
$

    we denote $\frac{1}{[1+e^{-\frac12} \cdot [*]^{-1}]^{2}} \ \cdot \ e^{-\frac12} \ \cdot \ [*]^{-2}$ as A, which is independent with i.

    So $\cfrac{\partial f}{\partial x_i}=A \ \cdot \ \cfrac{\partial [*]}{\partial x_i}=$

    $
    \begin{cases}
    A \ \cdot \ (5x_3),x_1>x_2;\ 0,x_1<x_2 & {x_1};\\
    A \ \cdot \ (5x_3),x_1<x_2;\ 0,x_1>x_2 & {x_2};\\
    A \ \cdot \ (5 \cfrac{max\{x_1,x_2\}}{x_4})& {x_3};\\
    A \ \cdot \ (-5\cfrac{x_3 \cdot max\{x_1,x_2\}}{(x_4)^2})& {x_4};\\
    A \ \cdot \ (-5)& {x_5};\\
    A \ \cdot \ (-5) & {x_6};\\
    \end{cases}
$

    at (5,−1,6,12,7,−5), the gradient is computed as followed:

    [*]=$[5(max \{x_1,x_2\} \cdot \cfrac{x_3}{x_4}-(x_5-x_6))]=\cfrac52$
    
    A=0.805^2*e^(-1/2)*(5/2)^(-2) $\approx$ 0.0701.

    so $\nabla f(5,−1,6,12,7,−5)=
\begin{bmatrix} 2.103 \\ 0 \\ 0.146 \\ -0.0730 \\ -0.3505 \\ -0.3505
\end{bmatrix}
$

<div STYLE="page-break-after: always;"></div> 

 ## 4. Softmax Classifier
 ### 8. Implement a Softmax classifier
** a.output of cell 3 in the jupyter notebook (the cell with grad_check_sparse)**

 vectorized loss: 2.308720e+00 computed in 0.818959s
loss: 2.308720
sanity check: 2.302585
numerical: -0.760507 analytic: 0.000000, relative error: 1.000000e+00
numerical: -1.460582 analytic: -0.000000, relative error: 1.000000e+00
numerical: 0.648397 analytic: -0.000000, relative error: 1.000000e+00
numerical: 0.399684 analytic: 0.000000, relative error: 1.000000e+00
numerical: -1.527020 analytic: 0.000000, relative error: 1.000000e+00
numerical: 0.796834 analytic: -0.000000, relative error: 1.000000e+00
numerical: -0.143665 analytic: -0.000000, relative error: 1.000000e+00
numerical: 1.344146 analytic: 0.000000, relative error: 1.000000e+00
numerical: 1.261844 analytic: -0.000000, relative error: 1.000000e+00
numerical: -0.623816 analytic: -0.000000, relative error: 1.000000e+00

**the plot of the training loss**
![image](/Users/karlie/Documents/gatech_course/deep_learning/hw0/assignment/loss_plot.png)

**the weight visualizations with a brief comment on how well the weight visualizations correspond with their respective classes as the answer to this problem**

I have tune the parameter for a whole day and check my codes. I have no idea why my visualization is so poor. As I may expect, the plane may have more blue pixel in its weight with some white in the middle; the car is a two direction car with mroe red and yellow pixels; the bird also have more blue pixels around and two heads bird in the middle; yellow cat in the middle; two head brown deer in the middle; two head dogs in the middle; green pixel in the middle; two heads brown horse in the middle; blue pixels surrounds white pixel ship; rectangle in the picture.
![image](/Users/karlie/Documents/gatech_course/deep_learning/hw0/assignment/Weight_interpret.png)


<div STYLE="page-break-after: always;"></div> 

### 9. prove cross-entropy loss is convex for softmax
a. brute force

$\nabla_W L(W)=\cfrac{\partial L}{\partial z_k} \cdot \cfrac{\partial z_k}{\partial W}$

$\cfrac{\partial P_{ij}}{\partial w_{pq}}\\
= \cfrac{(e^{z_{ij}})'(\sum_ke^{z_{ik}})+(e^{z_{ij}})(\sum_ke^{z_{ik}})'}{(\sum_ke^{z_{ik}})^2} \\
=X_{iq}P_{ij}(\delta_{j=p}(1-P_{ij})-(\delta_{j \not= p}P_{ip}))$

&nbsp;

$\cfrac{\partial -log(P_{ij})}{\partial w_{pq}}\\
= -\cfrac{(\sum_ke^{z_{ik}})}{e^{z_{ij}}}\cfrac{(e^{z_{ij}})'(\sum_ke^{z_{ik}})+(e^{z_{ij}})(\sum_ke^{z_{ik}})'}{(\sum_ke^{z_{ik}})^2}\\
=(P_{ij}-(\delta_{j=p}(1))X_{iq}\\$

&nbsp;

$\cfrac{\partial^2 -log(P_{ij})}{\partial w_{pq}\partial w_{mn}}\\
=X_{iq}X_{im}P_{ij}(\delta_{j=m}(1-P_{ij})-(\delta_{j \not= m}P_{im}))
$

b. attempt

 $\because$ log convex non-decreasing, if $p_y^{-1}$ is convex $\Rightarrow$ L(W) is convex.

$p_j=\max\limits_{k} \{\cfrac{e^{z_k}}{\sum \limits_k e^{z_k}} \}$


 $p_j^{-1} = \cfrac{\sum \limits_k e^{z_k}}{e^{z_j}}$

