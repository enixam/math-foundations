
# (PART) Multivariate Calculus {-}

# Partial Derivatives

## Limit and Continuity 

Limits and continuity in one dimension

Limits and continuity in higher dimensions

## Partial Derivative 



### Gradient and Directional Derivative  

We want to know the instant rate of change at $P_0 = (x_0, y_0)$, when moving towards the direction $\bar{u} = [u_1, u_2]$ a tiny step of length $h$. 


\BeginKnitrBlock{definition}\iffalse{-91-68-105-114-101-99-116-105-111-110-97-108-32-100-101-114-105-118-97-116-105-118-101-93-}\fi{}<div class="definition"><span class="definition" id="def:directional-derivative"><strong>(\#def:directional-derivative)  \iffalse (Directional derivative) \fi{} </strong></span>$$
\Big(\frac{df}{dh} \Big)_{\bar{u}, P_0}  = \lim_{h \to 0} \frac{f(x_0 + hu_1, y_0 + hu_2) - f(x_0, y_0)}{h}
$$</div>\EndKnitrBlock{definition}



The concise version using vector notation is 

$$
\lim_{h \to 0} \frac{f(\bar{x}  +  h\bar{u}) - f(\bar{x})}{h}
$$


$$
x = x_0 + hu_1, \quad y = y_0 + hu_2
$$

use the chain rule 
$$
\begin{split}
\Big(\frac{df}{dh} \Big)_{\bar{u}, P_0}  &= \frac{\partial f}{\partial x} \biggr |_{P_0} \frac{dx}{dh} +      \frac{\partial f}{\partial y} \biggr |_{P_0} \frac{dy}{dh} \\
&= \frac{\partial f}{\partial x} \biggr |_{P_0}u_1 + \frac{\partial f}{\partial y} \biggr |_{P_0}u_2 \\
&= \nabla f |_{P_0} \cdot \bar{u}
\end{split}
$$
Expand the dot product, we get 

$$
D_{\bar{u}}f = |\nabla f| |\bar{u}| \cos\theta = |\nabla f| \cos\theta
$$


\BeginKnitrBlock{theorem}\iffalse{-91-80-114-111-112-101-114-116-105-101-115-32-111-102-32-100-105-114-101-99-116-105-111-110-97-108-32-100-101-114-105-118-97-116-105-118-101-115-93-}\fi{}<div class="theorem"><span class="theorem" id="thm:property-directional-derivative"><strong>(\#thm:property-directional-derivative)  \iffalse (Properties of directional derivatives) \fi{} </strong></span>That function $f$ increases most rapidly in the direction of the gradient vector $\nabla f$ at $P$. The directional derivative (instant increasing rate of change) in this direction is 

$$
D_{\bar{u}}f = |\nabla f| \cos{0} = |\nabla f|
$$

Likewise, $f$ decreases most rapidly in the direction of $-\nabla f$. The directional derivative in this direction is 

$$
D_{\bar{u}}f = |\nabla f| \cos{\pi} = - |\nabla f|
$$</div>\EndKnitrBlock{theorem}




### Linearization of Two-variable Functions 

Linearization of univariate function $f(x)$ centered at $x = a$ is the point-slope equation

$$
L(x) = f(a) + f'(a)(x - a) 
$$

Now we move to functions of two variables. Suppose a differentiable function $f(x, y)$ and its partial derivatives exist at a point $f(x_0, y_0)$. If we move to a nearby point $(x_0 + \Delta x, y_0 + \Delta y)$, the change in $f$ is 

$$
\Delta f = f(x_0 + \Delta x, y_0 + \Delta y) - f(x_0, y_0) 
$$

Like in the single variable case (Eq \@ref(eq:one-differential)), the change in $f$ is 

$$
f(x, y) - f(x_0, y_0) = f_x \Delta x + f_y \Delta y + \varepsilon_1\Delta x + \varepsilon_2 \Delta y
$$
where $\varepsilon_1, \varepsilon_2 \to 0$ as $\Delta x, \Delta y \to 0$. When $\Delta x, \Delta y \to 0$, the error term will be even smaller and we have the linear approximation 

$$
f(x, y) \approx L(x, y) = f(x_0, y_0) + f_x (x - x_0) + f_y  (y - y_0)
$$
\BeginKnitrBlock{definition}<div class="definition"><span class="definition" id="def:two-linearization"><strong>(\#def:two-linearization) </strong></span>The **Linearization** of a function $f(x, y)$ at a differentiable point $(x_0, y_0)$ is 

$$
L(x, y ) = f(x_0, y_0) + f_x (x - x_0) + f_y (y - y_0) 
$$
The approximation 
$$
f(x, y) \approx L(x, y)
$$
is called the **standard linear approximation** of $f$ at $(x_0, y_0)$</div>\EndKnitrBlock{definition}

In the two variable case, $L(x, y)$ denotes a plane tangent to the surface $z = f(x, y)$ at point $(x_0, y_0)$



## Differentials 

We first review the definition of differential in single variable calculus. In single variable calculus, the change in function $f$ as $x$ changes from $a$ to $a + \Delta x$ is 
$$
\Delta y = f(a + \Delta x) - f(a)
$$

The corresponding change in the standard linearization $L(x)$ from $a$ to $a + \Delta x$ is 

$$
\begin{split}
\Delta L &= \underbrace{f(a) + f'(a)(a + \Delta x - a)}_{L(a + \Delta x)} - \underbrace{f(a)}_{L(a)} \\
&= f'(a)\Delta x
\end{split}
$$


When $\Delta x$ is a infinitely small number $dx$ (but nonzero), we can use $\Delta L$ to approximate $\Delta y$. In such a case, let $dy$ or $df$ represents the the amount the tangent line rises or falls when $x$ changes by an tiny amount $\Delta x = dx$. This amount is called a *differential*. In other words, the differential $dy$ is the change $\Delta L$ in the linearization of $f$ when $x = a$ changes by an amount $dx$.  

Now let $a$ be any point $x$ in $f$'s domain, the differential $dy$ (or $df$) is

$$
dy = f'(x)\Delta x
$$
The error between $\Delta y$ (true change) and $dy$ (approximate change) at $x = a$ is given by

$$
\begin{split}
\Delta y - dy &= \underbrace{f(a + \Delta x) - f(a)}_{\text{true change}}  - \underbrace{f'(a)\Delta x}_{\text{approximate change}} \\
&= \underbrace{\Big(\frac{f(a + \Delta x) - f(a)}{\Delta x} - f'(a)\Big)}_{\varepsilon} \Delta x \\
&= \varepsilon \Delta x
\end{split}
$$

when $\Delta x \to 0$, the difference quotient 

$$
\frac{f(a + \Delta x) - f(a)}{\Delta x} \to f'(a)
$$
Thus $\varepsilon \to 0$ as $\Delta x \to 0$, and $\Delta y$ can be reexpressed as 

\begin{equation}
(\#eq:one-differential)
\Delta y = dy + \varepsilon \Delta x = f'(a)\Delta x + \varepsilon \Delta x
\end{equation}

<br> 


In the two variable case,  the change in linearization is 

$$
\Delta L =  f_x \Delta x + f_y \Delta y
$$
We take $dx = \Delta x$ and $dy = \Delta y$. We then have the following definition of the *differential* or *total differential* of $f$. 

\BeginKnitrBlock{definition}<div class="definition"><span class="definition" id="def:differential"><strong>(\#def:differential) </strong></span>When moving from $(x_0, y_0)$ to a nearby point $(x_0 + dx, y_0  + dy)$, the resulting change 

$$
df = f(x_0, y_0) + f_xdx + f_y dy
$$
in the linearization of $f$ is called the **total differential of $f$**.</div>\EndKnitrBlock{definition}




### Continuity, Partial Derivatives and Differentiability



## Divergence, Curl, and Laplacian

 

