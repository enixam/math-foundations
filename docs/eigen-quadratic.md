
# Eigenthings and quadratic forms


## Eigenvectors and eigenvalues  

\BeginKnitrBlock{definition}\iffalse{-91-69-105-103-101-110-118-101-99-116-111-114-115-32-97-110-100-32-101-105-103-101-110-118-97-108-117-101-115-93-}\fi{}<div class="definition"><span class="definition" id="def:eigen"><strong>(\#def:eigen)  \iffalse (Eigenvectors and eigenvalues) \fi{} </strong></span>An **eigenvector** of an $n \times n$ matrix $A$ is a *nonzero* vector $\boldsymbol{x}$ such that $A\boldsymbol{x} = \lambda\boldsymbol{x}$. 

$\lambda$ is the **eigenvalue** of $A$ if there is a nontrivial solution $\boldsymbol{x}$ of $A\boldsymbol{x} = \lambda \boldsymbol{x}$; such an $\boldsymbol{x}$ is called an *eigenvector corresponding to $\lambda$*</div>\EndKnitrBlock{definition}

To find eigenvalues and corresponding eigenvectors of $A$, we look at the equation 

$$
(A - \lambda I)\boldsymbol{x}= 0
$$

Since eigenvector $\boldsymbol{x}$ must be nonzero, $(A - \lambda I)$ is a singular matrix 


\begin{equation}
(\#eq:characteristic-equation)
\det (A - \lambda I) = 0
\end{equation}

Eq \@ref(eq:characteristic-equation) is called the **characteristic equation** of matrix $A$. This is a scalar equation containing information about eigenvalues and eigenvectors of a square matrix $A$. 



\BeginKnitrBlock{theorem}<div class="theorem"><span class="theorem" id="thm:unnamed-chunk-1"><strong>(\#thm:unnamed-chunk-1) </strong></span>Eigenvalues of a trangular matrix are its diagonal entries.</div>\EndKnitrBlock{theorem}


**PROOF**  

Consider the $3 \times 3$ case. If $A$ is upper triangular, then $A - \lambda I$ has the form 

$$
\begin{bmatrix}
a_{11} - \lambda & a_{12} & a_{13} \\
0 & a_{22} - \lambda & a_{23}  \\
0 & 0 & a_{33} - \lambda
\end{bmatrix}
$$
So the roots of characteristic are $a_{11}, a_{22}, a_{33}$ respectively. 

There are some useful results about how eigenvalues change after various manipulations. 

1. For any $k, b \in \mathbb{R}$, $\boldsymbol{x}$ is an eigenvector of $kA + bI$ with eigenvalue $k\lambda + b$  

**PROOF**
$$
(kA + bI)\boldsymbol{x} = kA\boldsymbol{x} + bI\boldsymbol{x} = k \lambda\boldsymbol{x} + b\boldsymbol{x} = (k\lambda + b)\boldsymbol{x} 
$$


2, If $A$ is invertible, then $\boldsymbol{x}$ is an eigenvector of $A^{-1}$ with eigenvalue $1/\lambda$  

**PROOF**

$$
\boldsymbol{x} = A^{-1}A\boldsymbol{x} =  A^{-1}\lambda \boldsymbol{x} = \lambda A^{-1}\boldsymbol{x}
$$
3. $A^{k}\boldsymbol{x} = \lambda^{k}\boldsymbol{x}$ 


The next theorem is important in terms of diagonalization and spectral decomposition

\BeginKnitrBlock{theorem}<div class="theorem"><span class="theorem" id="thm:distinct-eigenvalue"><strong>(\#thm:distinct-eigenvalue) </strong></span>For distinct eigenvalues $\lambda_1, \cdots, \lambda_r$ of an $n \times n$ matrix A, their corresponding eigenvectors $\boldsymbol{v_1}, ..., \boldsymbol{v_r}$ are linearly independent. </div>\EndKnitrBlock{theorem}

**PROOF**  

Suppose for r distinct eigenvalue  $\lambda_1, \cdots, \lambda_r$, the set $\{\boldsymbol{v_1}, ..., \boldsymbol{v_r}\}$ is not linearly independent, and $p$ is the least index such that $\boldsymbol{v}_{p+1}$ is a linear combination of the preceding vectors. Then there exists scalars $c_1, \cdots, c_p$ such that

$$
c_1\boldsymbol{v}_1 + \cdots + c_p\boldsymbol{v}_p = \boldsymbol{v}_{p+1} \tag{1}
$$
Left multiply by $A$, and note we have $A\boldsymbol{v}_i = \lambda_i\boldsymbol{v}_i$ for $i = 1, ..., n$ 

$$
c_1\lambda_1\boldsymbol{v}_1 + \cdots + c_p\lambda_p\boldsymbol{v}_p = \lambda_{p+1}\boldsymbol{v}_{p+1} \tag{2}
$$
Multiplying both sides of (2) by $\lambda_{p+1}$ and subtracting (2) from the result 

$$
c_1(\lambda_1 - \lambda_{p+1})\boldsymbol{v}_1 +\cdots + c_p(\lambda_p - \lambda_{p+1})\boldsymbol{v}_p = 0 \tag{3}
$$
Since $\boldsymbol{v}_1, ..., \boldsymbol{v}_p$ are linearly independent,  weights in (3) must be all zero. Since $\lambda_1, \cdots, \lambda_p$ are distinct, hence $c_i = 0, \, i = 1, ..., p$. But then (5) says that eigenvector $\boldsymbol{v}_{p+1}$ is zero vector, which contradicts definition \@ref(def:eigen)   

<hr>


```propisition
Let $A in \mathbb{R}^{m \times n}$ $A^TA_{n \times n}$ and $AA^T$ has the same set of *nonzero* eigenvalues. 
```

**PROOF** 

Let $\lambda$ be a nonzero eigenvalue of $A^TA$ and $\boldsymbol{x}$ its eigenvector 

$$
\begin{split}
(A^TA)\boldsymbol{x} &= \lambda\boldsymbol{x} \\
\end{split}
$$
Left multiply by $A$ 

$$
AA^T(A\boldsymbol{x}) = \lambda (A\boldsymbol{x})
$$
We will have to verify that $A\boldsymbol{x}$ is no zero vector before concluding $\lambda$ is also an eigenvector of $AA^T$. Suppose $A\boldsymbol{x} = 0$, then $A^TA\boldsymbol{x} =\lambda\boldsymbol{x} = 0$. Since $\boldsymbol{x}$ is a eigenvector which is nonzero, $\lambda = 0$, which contradicts our former statement. Thus, any nonzero eigenvalue of $A^TA$ is also an eigenvalue of $AA^T$. 

## Additional properties of eigenvalues and eigenvectors  

Let $A \in \mathbb{R}^{n \times n}$ with eigenvalues $\lambda_1, ..., \lambda_n$. Here are some additional properties of this matrix and its eigenvlaues: 

- The trace of $A$ is the sum of all eigenvalues

$$
\text{tr}(A) = \sum_{i=1}^{n}{\lambda_i}
$$

- The determinant of $A$ is the product of all its eigenvalues.  

$$
\det(A) = \prod_{i=1}^{n}{\lambda_i}
$$

- The eigenvalues of $k$th power of $A$, i.e. $A^k$, is $\lambda_1^k, ..., \lambda_n^k$  

- If $A$ is invertible, then eigenvalues of $A^{-1}$ are $\frac{1}{\lambda_1}, ..., \frac{1}{\lambda_n}$  

- For a polynomial function $P$ the eigenvalues of $P(A)$ are $P(\lambda_1), ..., P(\lambda_n)$




## Diagnolization and similar matrices 


\BeginKnitrBlock{definition}\iffalse{-91-68-105-97-103-111-110-97-108-105-122-97-116-105-111-110-32-116-104-111-101-114-101-109-93-}\fi{}<div class="definition"><span class="definition" id="def:diagonalization"><strong>(\#def:diagonalization)  \iffalse (Diagonalization thoerem) \fi{} </strong></span>An $n \ times n$ matrix $A$ is diagnolizable **if and only if** A has $n$ independent linearly independent eigenvectors. 

In such case, in $A = P \Lambda P^{-1}$, the diagonal entries of $D$ are eigenvalues that correpond, respectively, to the eigenvectors of in $P$  
  
In other words, $A$ is diagnolizable if and only if there are enough eigenvectors in form a basis of $R^n$, called an **eigenvector basis** of $R^n$ </div>\EndKnitrBlock{definition}

**Proof** 

$$
\begin{split}
AP &= A[\boldsymbol{v}_1 \cdots \boldsymbol{v}_n] \\
   &= [A\boldsymbol{v}_1 \cdots A\boldsymbol{v}_n] \\ 
   &= [\lambda_1\boldsymbol{v}_1 \cdots \lambda_n\boldsymbol{v}_n]
\end{split}
$$
while on the other side of the equation:  

$$
\begin{aligned}
DP &= 
[\boldsymbol{v}_1 \cdots \boldsymbol{v}_n]
\begin{bmatrix}
\lambda_1 & 0 & \cdots & 0\\
0  & \lambda_2 & \cdots & 0 \\
\vdots & \vdots & & \vdots \\
0 & 0 & \cdots & \lambda_n 
\end{bmatrix} 
 \\
&= [\lambda_1\boldsymbol{v}_1 \cdots \lambda_n\boldsymbol{v}_n]
\end{aligned}
$$

So that 

$$
\begin{aligned}
AP &= PD \\
A &= P \Lambda P^{-1}
\end{aligned}
$$
Because $P$ contains $n$ independent columns so it's invertible.  

According to theorem \@ref(thm:distinct-eigenvalue), an $n \times n$ matrix with $n$ distinct eigenvalues is diagonalizable. This is a sufficient condition. 

For matrices whose eigenvalues are not distinct, there is still a change that it is diagonalizable. For any matrix $A_{n\times n}$, as long as the sum of the dimensions of the eigenspaces equals $n$ then $P$ is invertible. This could happen in the following two scenarios

1. The characteristic polynomial factors completely into linear factors. This is the case when $A$ has n distinct eigenvalues. 

2. The dimension of the eigenspace for each $\lambda_k$ equals the multiplicity of $\lambda_k$. Thus $A$ with repeated eigenvalues can still be diagonalizable. 

### Similarity

If $A$ and $B$ are both $n \times n$ matrices, then $A$ **is similar to** $N$ if there is an invertible matrix $P$ such that $P^{-1}AP = B$, or equivalently if we write $Q$ for $P^{-1}$, $Q^{-1}BQ = A$. Changing $A$ into $P^{-1}AP$ is called a **similarity transformation**.  




\BeginKnitrBlock{theorem}<div class="theorem"><span class="theorem" id="thm:unnamed-chunk-3"><strong>(\#thm:unnamed-chunk-3) </strong></span>If $A$ and $B$ are similar, they have the same eigenvalues. </div>\EndKnitrBlock{theorem}

**PROOF**  
If $B = P^{-1}AP$, then 

$$
B - \lambda I = P^{-1}AP - \lambda P^{-1}P = P^{-1}(AP - \lambda P) =  P^{-1}(A - \lambda I) P
$$
so that 

$$
\det (B - \lambda I ) = \det(P) \cdot \det(A - \lambda I ) \cdot \det(P^{-1})
$$
since $\det(P) \cdot \det(P^{-1}) = \det (I) = 1$, we have 

$$
\det (B - \lambda I)  = \det(A - \lambda I)
$$

As a result of their identical characteristic polynomial, $B$ and $A$ have the same eigenvalues. We can also show that eigenvector of $B$ is $P\boldsymbol{v}$:

$$
\begin{aligned}
A\boldsymbol{v} &= \lambda\boldsymbol{v} \\
(P^{-1}BP)\boldsymbol{v} &= \lambda\boldsymbol{v} \\
P(P^{-1}BP)\boldsymbol{v} &= \lambda P\boldsymbol{v} \\
B(P\boldsymbol{v}) = \lambda P \boldsymbol{v}
\end{aligned}
$$



The similarity theorem leads to a interesting proposition. 

\BeginKnitrBlock{proposition}<div class="proposition"><span class="proposition" id="prp:unnamed-chunk-4"><strong>(\#prp:unnamed-chunk-4) </strong></span>For $A, B \in \mathbb{R}^{n \times n}$, $AB$ and $BA$ are similar matrices and therefore share the same set of eigenvalues.  </div>\EndKnitrBlock{proposition}

To prove this, we need to show that there exists a invertible matrix $A$ such that $P^{-1}(AB)P = BA$. Take $P = A$ and the equation holds.  

It is easy to show that similarity is **transitive**: if $A$ is similar to $B$, $B$ is similar to $C$, then $A$ is similar to $C$. So similarity means a family of matrices with the same set of eigenvalues, the most special and simplest of which is the diagonal matrix (if this is an diagonalizable family). Some computer algorithms calculate eigenvalues of $A$ in this manner: with a sequential choices of $P$, the off-diagonal elements of $A$ become smaller and smaller until $A$ becomes a triangular matrix or diagonal matrix, whose eigenvalues are simply diagonal entries and is the same as $A$.


It is obvious that a diagonalizable matrix $A$ is similar to diagonal matrix $D$, whose diagonal entries are $A$'s eigenvalues $\lambda_i$, and $P = [\boldsymbol{v}_1 \;\; \cdots \;\; \boldsymbol{v}_n]^{-1}$ where $\boldsymbol{v}_i, \;i = 1,..., n$ are eigenvectors corresponding to $\lambda_i$. 

But square matrix $A$ can still be similar to matrices other than $D$ with other choices of $P$, and non-diagonal matrices can also have similar matrices of their own. In fact, **every square matrix is similar to a matrix in Jordan matrix** \@ref(jordan-matrix). 


<hr>

Similarity is only a *sufficient* condition for identical eigenvalues. The matrices 

$$
\begin{bmatrix}
2 & 1 \\
0 & 2 
\end{bmatrix}
\;\text{and}\;
\begin{bmatrix}
2 & 0 \\
0 & 2 
\end{bmatrix}
$$
are not similar even though they have the same eigenvalues. 


### Jordan matrix

For non-diagonalizable matrices $A_{n \times n}$, the goal is to with similar transformation $P^{-1}AP$ construct a matrix that is as nearest to a diagonal matrix as possible.  


\BeginKnitrBlock{definition}<div class="definition"><span class="definition" id="def:unnamed-chunk-5"><strong>(\#def:unnamed-chunk-5) </strong></span>The $n \times n$ matrix $J_{\lambda, n}$ with $\lambda$s on the diagonal, $1$s on the superdiagonal and $0$s elsewhere is called a Jordan matrix. A Jordan matrix in Jordan normal form is a block matrix that has Jordan blocks down its block diagonal and is zero elsewhere</div>\EndKnitrBlock{definition}

An example of Jordan matrix, the appearance of $\lambda_i$ on the diagonal is equal to its multiplicity as $A$'s eigenvalue. 
$$
\begin{bmatrix}
\lambda_1 & 1  & \\
& \lambda_1 & 1 & \\
& & \lambda_1 & \\ 
& & & \lambda_2 & 1 \\
& & & & \lambda_2  \\ 
& & & & & \lambda_3 & 1  \\ 
& & & & & & \ddots \\
& & & & & & & \lambda_n & 1 \\
& & & & & & & & \lambda_n
\end{bmatrix}
$$
An illustration from [wikipedia](https://en.wikipedia.org/wiki/Jordan_normal_form), the circled area is the Jordan blcok. 
<img src="images/jordan-blocks.png" width="40%" style="display: block; margin: auto;" />

Though the purpose of this section was not the computation details of Jordan matrices, it helps to give a concrete example. Consider $A$

$$
A = 
\begin{bmatrix}
5 & 4 & 2 & 1 \\
0 & 1 & -1 & -1 \\
-1 & -1 & 3 & 0 \\
1 & 1 & -1 & 2
\end{bmatrix}
$$

Including multiplicity, the eigenvalues of $A$ are $\lambda = 1, 2, 4, 4$. And for $\lambda = 4$, the eigenspace is 1 dimensional instead of 2, meaning $A$ is not diagonalizable. Nonetheless, $A$ is similar to the following Jordan matrix 

$$
J = 
\begin{bmatrix}
1 & 0 & 0 & 0\\
0 & 2 & 0 & 0\\
0 & 0 & 4 & 1\\
0 & 0 & 0 & 4
\end{bmatrix}
$$

To obtain $P$, recall that $P^{-1}AP = J$. Let $P$ have column vectors $p_i, \; i = 1,...,4$, then:

$$
A[\boldsymbol{p}_1 \; \; \boldsymbol{p}_2 \;\; \boldsymbol{p}_3 \;\; \boldsymbol{p}_4] = [\boldsymbol{p}_1 \; \; \boldsymbol{p}_2 \;\; \boldsymbol{p}_3 \;\; \boldsymbol{p}_4]
\begin{bmatrix}
1 & 0 & 0 & 0\\
0 & 2 & 0 & 0\\
0 & 0 & 4 & 1\\
0 & 0 & 0 & 4
\end{bmatrix}
= [\boldsymbol{p}_1 \;\; 2\boldsymbol{p}_2 \;\; 4\boldsymbol{p}_3 \;\; \boldsymbol{p}_3 + 4\boldsymbol{p}_4]
$$

We see that 

$$
\begin{aligned}
(A - 1I)\boldsymbol{p}_1 &= \boldsymbol{0} \\
(A - 2I)\boldsymbol{p}_2 &= \boldsymbol{0} \\
(A - 4I)\boldsymbol{p}_3 &= \boldsymbol{0} \\
(A - 1I)\boldsymbol{p}_4 &= \boldsymbol{p}_3 
\end{aligned}
$$
The solutions $\boldsymbol{p}_i$ are called **generalized eigenvectors** of $A$. 

## Symmetric matrices 

A *square* matrix $A \in \mathbb{R}^{n \times n}$ is *symmetric* if $A = A^{T}$, and *anti-symmetric* if $A = - A^{T}$. 

It can be shown that for any $A \in \mathbb{R}^{n \times n}$, $A + A^T$ is symmetric and $A - A^T$ anti-symmetric. So any square matrix $A$ can be wrote as a sum of a symmetric matrix and an anti-symmetric matrix 

$$
A = \frac{1}{2}(A + A^T) + \frac{1}{2}(A - A^T)
$$

It is common to denote the set of all symmetric matrices of size $n$ as $\mathbb{S}^n$, and $A \in \mathbb{S}^n$ means $A$ is a symmetric $n \times n$ matrix. 


Symmetric matrices have some nice properties about diagonalization.  

\BeginKnitrBlock{theorem}<div class="theorem"><span class="theorem" id="thm:unnamed-chunk-7"><strong>(\#thm:unnamed-chunk-7) </strong></span>If $A$ is symmetric, eigenvectors from distinct eigenvalues are **orthogonal**. </div>\EndKnitrBlock{theorem}

**PROOF** 

Let $\boldsymbol{v}_1$ and $\boldsymbol{v}_2$ be eigenvectors that correspond to distinct eigenvalues $\lambda_1$ and $\lambda_2$. Compute 

$$
\begin{split}
\lambda_1\boldsymbol{v}_1 \cdot \boldsymbol{v}_2 &= (\lambda_1\boldsymbol{v}_1)^T\boldsymbol{v}_2 \\
&= (\boldsymbol{v}_1^TA^T)\boldsymbol{v}_2 \\
&= \boldsymbol{v}_1^T(A\boldsymbol{v}_2) \\
&= \boldsymbol{v}_1^T(\lambda_2\boldsymbol{v}_2) \\
&= \lambda_2\boldsymbol{v}_1 \cdot \boldsymbol{v}_2
\end{split}
$$
because $\lambda_1 \not = \lambda_2$, $\boldsymbol{v}_1 \cdot \boldsymbol{v}_2 = 0$.

For symmetric matrices $A \in \mathbb{R}^{n \times n}$ without $n$ distinct eigenvalues, it turns out that the dimension of the eigenspace for each $\lambda_k$ always equals the multiplicity of $\lambda_k$. For this reason, if $A$ is a symmetric matrix we can always construct a orthonormal set $\{\boldsymbol{q}_1 \;\; \cdots \;\; \boldsymbol{q}_n\}$ from $\{\boldsymbol{v}_1 \;\; \cdots \;\; \boldsymbol{v}_n\}$ such that  

$$
Q^{T} = 
\begin{bmatrix}
\boldsymbol{q}_1^T \\
\vdots \\ 
\boldsymbol{q}_n^T
\end{bmatrix}
= Q^{-1}
$$
Recall that matrix $A$ with $n$ linearly independent eigenvectors is diagonalizable and can be written as 

$$
A = P \Lambda P^{-1}
$$
where $P = [\boldsymbol{v}_1 \;\; \cdots \;\; \boldsymbol{v}_n]$ and $\Lambda$ is a diagonal matrix with eigenvalues on its diagonal entries. 

With symmetric matrices, $\{\boldsymbol{v}_1, \cdots, \boldsymbol{v}_n\}$ must be linearly independent and can be transformed into a orthonormal basis $\{\boldsymbol{q}_1, \cdots, \boldsymbol{q}_n\}$. With orthogonal matrix $Q =[\boldsymbol{q}_1 \;\; \cdots \;\; \boldsymbol{q}_n]$, we have

\begin{equation}
(\#eq:orthogonal-diagonalization)
A = Q \Lambda Q^{T}
\end{equation}

Such matrix $A$ is said to be **orthogonally diagonalizable**. 

We have seen that for symmetric matrix $A$, Eq \@ref(eq:orthogonal-diagonalization) always holds. We can also also verify that if $A$ is orthogonally diagonalizable then it is a symmetric matrix

$$
A^T = (Q \Lambda Q^{T})^T = (Q^T)^T\Lambda^TQ^T= Q \Lambda Q^{T}  = A
$$

\BeginKnitrBlock{theorem}<div class="theorem"><span class="theorem" id="thm:unnamed-chunk-8"><strong>(\#thm:unnamed-chunk-8) </strong></span>An $n \times n$ matrix $A$ is orthogonally diagonalizable if an only if $A$ is a symmetric matrix. </div>\EndKnitrBlock{theorem}

### Spectral decomposition 

For orthogonally diagonalizable matrix $A$, we have 

$$
A = Q \Lambda Q^{T} = [\boldsymbol{q}_1 \;\; \cdots \;\; \boldsymbol{q}_n] 
\begin{bmatrix}
\lambda_1 & & \\
 & \ddots \\
 & & \lambda_n
\end{bmatrix}
\begin{bmatrix}
\boldsymbol{q}_1^T \\
\vdots \\
\boldsymbol{q}_n
\end{bmatrix}
$$

It follows that 

\begin{equation}
(\#eq:spectral-decomposition)
A = \lambda_1\boldsymbol{q}_1\boldsymbol{q}_1^T + \cdots + \lambda_1\boldsymbol{q}_n\boldsymbol{q}_n^T
\end{equation}

Eq \@ref(eq:spectral-decomposition) is called the **spectral decomposition**, breaking $A$ into pieces of rank 1 matrix. It got this name because he set of eigenvalues of a matrix $A$ is sometimes called its *spectrum*.  




## Quadratic forms 

\BeginKnitrBlock{definition}\iffalse{-91-81-117-97-100-114-97-116-105-99-32-102-111-114-109-93-}\fi{}<div class="definition"><span class="definition" id="def:unnamed-chunk-9"><strong>(\#def:unnamed-chunk-9)  \iffalse (Quadratic form) \fi{} </strong></span>A **quadratic form** on $\mathbb{R}^n$ is a function $Q$ defined on $\mathbb{R}^n$ whose value at a vector $\boldsymbol{x}$ in $\mathbb{R}^n$ can be computed by an expression of the form $Q(\boldsymbol{x}) = \boldsymbol{x}^TA\boldsymbol{x}$, where $A \in \mathbb{R}^{n \times n}$ is a **symmetric** matrix. $A$ is called the matrix of the quadraticc form. </div>\EndKnitrBlock{definition}

There exists a one-to-one mapping between symmetric matrix $A$ and the quadratic form. Consider the $3 \times 3$ case: 

$$
\boldsymbol{x} =
\begin{bmatrix}
x_1 \\
x_3 \\
x_3 \\
\end{bmatrix}
, \;\; A = 
\begin{bmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33} 
\end{bmatrix} \\
$$

$$
\begin{split}
\boldsymbol{x}^TA\boldsymbol{x} &= 
[x_1 \;\; x_2 \;\; x_3]
\begin{bmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33} 
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_3 \\
x_3 \\
\end{bmatrix} \\
&= a_{11}x_1^2 + a_{22}x_2^2 + a_{33}x_3^2 + \\
& \quad(a_{12} + a_{21})x_1x_2 + (a_{13} + a_{31})x_1x_3 + (a_{23} + a_{32})x_2x_3 
\end{split} 
\tag{1}
$$
Since $A$ is symmetric, we have $a_{ij} = a_{ji}$, thus 

$$
\boldsymbol{x}^TA\boldsymbol{x}  = a_{11}x_1^2 + a_{22}x_2^2 + a_{33}x_3^2 + 2a_{12}x_1x_2 + 2a_{13}x_1x_3 + 2a_{23}x_2x_3 \tag{2} 
$$
This verifies that $\boldsymbol{x}^TA\boldsymbol{x}$ when $A \in \mathbb{R}^{n \times n}$ is symmetric does result in a quadratic function of $n$ variables. Conversely, any quadratic function of $n$ variables, like shown in $(2)$, can be expressed in terms of $\boldsymbol{x}^TA\boldsymbol{x}$ with unique choice of symmetric matrix $A \in \mathbb{R}^{n \times n}$.  

### Change of variabele 

If $\boldsymbol{x}$ is a variable vector in $\mathbb{R}^n$, then a *change of variable* is an equation of the form 

$$
\begin{aligned}
\boldsymbol{x} &= P\boldsymbol{y} \\
\text{or equivalently} \quad \boldsymbol{y} &= P^{-1}\boldsymbol{x}
\end{aligned}
$$
where $P$ is any invertible matrix $\in \mathbb{R}^{n \times n}$

\BeginKnitrBlock{theorem}\iffalse{-91-84-104-101-32-80-114-105-110-99-105-112-97-108-32-65-120-101-115-32-84-104-101-111-114-101-109-93-}\fi{}<div class="theorem"><span class="theorem" id="thm:principal-axes"><strong>(\#thm:principal-axes)  \iffalse (The Principal Axes Theorem) \fi{} </strong></span>Let $A$ be an $n \times n$ symmetric matrix. Then there exists an orthogonal change of variable, $\boldsymbol{x} = Q\boldsymbol{y}$, this transform the quadratic form $\boldsymbol{x}^TA\boldsymbol{x}$ into a quadratic form $\boldsymbol{y}^T\Lambda\boldsymbol{y}$ with no cross-product term.  

$Q$ is constructed with $A$'s orthonormal eigenvectors $\boldsymbol{q}_1, ..., \boldsymbol{q}_n$. According to theorem \@ref(eq:orthogonal-diagonalization): 

$$
\boldsymbol{x}^TA\boldsymbol{x} = (Q\boldsymbol{y})^TA(Q\boldsymbol{y}) = \boldsymbol{y}^TQ^{T}AQ\boldsymbol{y} = \boldsymbol{y}^T \Lambda \boldsymbol{y}
$$</div>\EndKnitrBlock{theorem}



The principal axes theorem \@ref(thm:principal-axes) shows that if $A$ is diagonalizable, quadratic form $\boldsymbol{x}^TA\boldsymbol{x}$ can be reexpressed into the form $\lambda_1y_1^2 + \lambda_2y_2^2 +  \cdots + \lambda_ny_n^2$ with change of variables $\boldsymbol{x} = Q\boldsymbol{y}$. 

### Classification of quadratic forms 

- A symmetric matrix $A \in \mathbb{S}^n$ is **positive definite** (PD) if for all non-zero vectors $\boldsymbol{x} \in \mathbb{R}^n,\; \boldsymbol{x}^TA\boldsymbol{x} > 0$. We can denote positive definite matrix $A$ as $A \succ 0$ (or $A > 0$). The set of all positive definite matrices is denoted as $\mathbb{S}_{++}^n$  

- A symmetric matrix $A \in \mathbb{S}^n$ is **positive semidefinite** (PSD) if for all non-zero vectors $\boldsymbol{x} \in \mathbb{R}^n,\; \boldsymbol{x}^TA\boldsymbol{x} \ge 0$. We can denote positive definite matrix $A$ as $A \succeq 0$ (or $A \ge 0$). The set of all positive semidefinite matrices is denoted as $\mathbb{S}_{+}^n$  

- A symmetric matrix $A \in \mathbb{S}^n$ is **negative definite** (ND), denoted by $A \prec 0$ (or $A < 0$),  if for all non-zero vectors $\boldsymbol{x} \in \mathbb{R}^n,\; \boldsymbol{x}^TA\boldsymbol{x} < 0$.  

- Similarly, a symmetric matrix $A \in \mathbb{S}^n$ is **negative semidefinite** (NSD), denoted by $A \preceq 0$ (or $A \le 0$),  if for all non-zero vectors $\boldsymbol{x} \in \mathbb{R}^n,\; \boldsymbol{x}^TA\boldsymbol{x} \le 0$.   

- Finally,  a symmetric matrix $A \in \mathbb{S}^n$ is **indefinite**, if it is neither positive semidefinite or negative semidefinite. In other words, if there exists $\boldsymbol{x}, \boldsymbol{x}', \in \mathbb{R}^{n}$ such taht $\boldsymbol{x}^TA\boldsymbol{x} > 0$ and $\boldsymbol{x'}^TA\boldsymbol{x}' > 0$

\BeginKnitrBlock{rmdnote}<div class="rmdnote">Note that when talking about $A$ being PD, PSD, ND, NSD or indefinite, $A$ is always assumed to be **symmetric**.

Also, if $A$ is positive definite, then $−A$ is negative definite and viceversa. Likewise, if $A$ is positive semidefinite then $−A$ is negative semidefinite and vice versa. If $A$ is indefinite, then so is $−A$. </div>\EndKnitrBlock{rmdnote}

From theorem \@ref(thm:principal-axes), we know that the sign of eigenvalues are closely related to classifications of symmetric matrices here. Take positive definite matrices for example, the following statements of $A$ are equivalent: 

- For any $\boldsymbol{x} \in \mathbb{R}^n, \; \boldsymbol{x}^TA\boldsymbol{x} > 0$  

- Let $\lambda_i, \; i = 1, ..., n$ be $A$'s eigenvalues, $\lambda_i > 0$  

- All leading determinants of $A > 0$  

- All pivots are $> 0$  


Classification of $A \in \mathbb{S}^{n}$ by its eigenvalue can be applied in general. 

\BeginKnitrBlock{theorem}\iffalse{-91-81-117-97-100-114-97-116-105-99-32-102-111-114-109-115-32-97-110-100-32-101-105-103-101-110-118-97-108-117-101-115-93-}\fi{}<div class="theorem"><span class="theorem" id="thm:unnamed-chunk-11"><strong>(\#thm:unnamed-chunk-11)  \iffalse (Quadratic forms and eigenvalues) \fi{} </strong></span>Let $A \in \mathbb{S}^{n}$. Then the quadratic form $\boldsymbol{x}^TA\boldsymbol{x}$ and $A$ is: 
   
- positive definite if and only if the eigenvalues of $A$ are all positive  

- negative definite if and only if the eigenvalues of $A$ are all negative  

- indefinite if and only if $A$ has both positive and negative eigenvalues</div>\EndKnitrBlock{theorem}


<hr>

\BeginKnitrBlock{proposition}<div class="proposition"><span class="proposition" id="prp:unnamed-chunk-12"><strong>(\#prp:unnamed-chunk-12) </strong></span>Given any matrix $A \in \mathbb{R}^{m \times n}$, $A^TA$ is a positive semidefinite matrix</div>\EndKnitrBlock{proposition}

**PROOF**

By definition, $A^TA$ is a positive semidefinite matrix if for any $\boldsymbol{x} \in \mathbb{R}^n$, the quadratic form $\boldsymbol{x}^T(A^TA)\boldsymbol{x} \ge 0$. 

$$
\begin{split}
\boldsymbol{x}^T(A^TA)\boldsymbol{x} &= (\boldsymbol{x}^TA^T)(A\boldsymbol{x}) \\
&= (A\boldsymbol{x})^T(A\boldsymbol{x}) \\
&= ||A\boldsymbol{x}||^2
\end{split}
$$
It turns out that the result is the square of the 2-norm of $A\boldsymbol{x}$ (nonnegative). This also tells $A^TA$ is positive definite when $\boldsymbol{x}$ is not in the null space of $A$. 


## Rayleigh quotients 

Let $A \in \mathbb{S}^n$ and $\boldsymbol{x} \in \mathbb{R}^n$, **Rayleigh quotient** is defined as 

$$
R_{A}(\boldsymbol{x}) = \frac{\boldsymbol{x}^TA\boldsymbol{x}}{\boldsymbol{x}^T\boldsymbol{x}}
$$
The Rayleigh quotient has some nice properties: 

- scale invariance: for any vector $\boldsymbol{x} \not= 0$ and any scalar $\alpha \not= 0$, $R_{A}(\boldsymbol{x}) = R_{A}(\alpha\boldsymbol{x})$  

- If $\boldsymbol{x}$ is a eigenvector of $A$ with eigenvalue $\lambda$, then $R_{A}(\boldsymbol{x}) = \lambda$

- The Rayleigh quotient is bounded by the largest and smallest eigenvalue of $A$, i.e. 

$$
\lambda_{\text{min}}(A) \le R_{A}(\boldsymbol{x}) \le \lambda_{\text{max}}(A)
$$

**PROOF** 

Since the Rayleigh quotient does not depend on the 2-norm of vector $\boldsymbol{x}$, we may assume a unit vector $\boldsymbol{x}^T\boldsymbol{x} = 1$, and Rayleigh quotient simplifies to the quadratic form $\boldsymbol{x}^TA\boldsymbol{x}$. 

Next, orthogonally diagonalize $A$ as $Q \Lambda Q$, we know that when $\boldsymbol{x} = Q \boldsymbol{y}$: 

$$
\boldsymbol{x}^TA\boldsymbol{x} = \boldsymbol{y}^T \Lambda \boldsymbol{y} \tag{1}
$$
Also 

$$
1= \boldsymbol{x}^T\boldsymbol{x} = (Q\boldsymbol{y})^T Q\boldsymbol{y} = \boldsymbol{y}^TQ^TQ\boldsymbol{y} = \boldsymbol{y}^T\boldsymbol{y} \tag{2}
$$

Expand $\boldsymbol{y}^T \Lambda \boldsymbol{y}$ in (1) we get 

$$
\boldsymbol{x}^TA\boldsymbol{x} = \lambda_1y_1^2 + \lambda_2y_2^2 + \cdots + \lambda_ny_n^2 \tag{3}
$$
where $\{\lambda_1, ..., \lambda_n\}$ are diagonal entries of $\Lambda$ and eigenvalues of $A$. Let us suppose that the set $\{\lambda_1, \lambda_2, \cdots, \lambda_n\}$ has already been ordered descendingly, so that $\lambda_1 > \lambda_2 > \cdots > \lambda_n$. 

We can obtain the inequality from (3) and the order of eigenvalues: 

$$
\begin{split}
\boldsymbol{x}^TA\boldsymbol{x} &= \lambda_1y_1^2 + \lambda_2y_2^2 + \cdots + \lambda_ny_n^2 \\
&\le \lambda_1y_1^2 + \underbrace{\lambda_1y_2^2 + \cdots + \lambda_1y_n^2}_{\lambda_1 \text{ is the greatest eigenvalue}} \\ 
&\le \lambda_1(\boldsymbol{y}^T\boldsymbol{y}) \\
&= \lambda_1
\end{split}
$$
The equation reach equality if and only if $[y_1, y_2, \cdots, y_n] = [1, 0, \cdots, 0]$. Since $\boldsymbol{x} = Q\boldsymbol{y}$, we have 

$$
\boldsymbol{x} = 
\begin{bmatrix}
\boldsymbol{q}_1 & \boldsymbol{q}_2 & \cdots & \boldsymbol{q}_n
\end{bmatrix}
\begin{bmatrix}
1 \\
0 \\
\vdots \\
0
\end{bmatrix}
= \boldsymbol{q}_1
$$
Similarly, the minimum of the Rayleigh quotient will be $\lambda_n$, with $\boldsymbol{x} = \boldsymbol{q}_n$. 


<hr>

From the optimization perspective, the bound of Rayleigh quotient amounts to a constrained optimization problem 

$$
\begin{aligned}
\text{objective function} &:  \boldsymbol{x}^TA\boldsymbol{x}\\
\text{subject to}&: \boldsymbol{x}^T\boldsymbol{x} = 1 
\end{aligned}
$$
The maximum and minimum of the objective function are $\lambda_1$ and $\lambda_n$, with $\boldsymbol{x}$ being $\boldsymbol{q}_1$ and $\boldsymbol{q}_n$ respectively. 

If we add more constraints, for example, that $\boldsymbol{x}$ should be orthogonal to $\boldsymbol{q}_1$, then $\boldsymbol{x}^TA\boldsymbol{x}$ has maximum $\lambda_2$ attained at $\boldsymbol{x} = \lambda_2$

\BeginKnitrBlock{theorem}<div class="theorem"><span class="theorem" id="thm:unnamed-chunk-13"><strong>(\#thm:unnamed-chunk-13) </strong></span>Let $A \in \mathbb{S}^n$ with orthogonal diagonalization $A = Q\Lambda Q^T$, where the entries on the diagonal of $\Lambda$ are arranged so that $\lambda_1 \ge \lambda_2 \ge \cdots \ge \lambda_n$. Then for $k = 2, ...$, the maximum of value of $\boldsymbol{x}^T A \boldsymbol{x}$ subject to constraints 

$$
\boldsymbol{x}^T\boldsymbol{x} =  1, \;\; \boldsymbol{x}^T\boldsymbol{q}_1 = 0, \;\; \dots \;\;, \boldsymbol{x}^T\boldsymbol{q}_{k-1} = 0
$$
is the eigenvalue $\lambda_k$, and this maximum is attained at $\boldsymbol{x} = \boldsymbol{q}_k$</div>\EndKnitrBlock{theorem}

**PROOF**

From $\boldsymbol{x} = P\boldsymbol{y}$ we know that

$$
\boldsymbol{x} = y_1\boldsymbol{q}_1 + \cdots + + y_{k-1}\boldsymbol{q}_{k-1} + y_k\boldsymbol{q}_k + \cdots +  y_{n}\boldsymbol{q}_n 
$$
Left multiply by $\boldsymbol{q}_1^T$ 

$$
\begin{aligned}
\boldsymbol{q}_1^T\boldsymbol{x} &= y_1\boldsymbol{q}_1^T\boldsymbol{q}_1 + \cdots + + y_{k-1}\boldsymbol{q}_1^T\boldsymbol{q}_{k-1} + y_k\boldsymbol{q}_1^T\boldsymbol{q}_k + \cdots +  y_{n}\boldsymbol{q}_1^T\boldsymbol{q}_n  \\
&= y_1\boldsymbol{q}_1^T\boldsymbol{q}_1 \\
&= y_1
\end{aligned} 
$$
Since $\boldsymbol{q}_1^T\boldsymbol{x} = \boldsymbol{x}^T\boldsymbol{q}_1 = 0$, we have $y_1 = 0$. Similarly, $y_2 = \cdots = y_{k-1} = 0$, and $\boldsymbol{y}$ becomes $[0 \;\; \cdots \;\; 0 \;\; y_{k} \;\; \cdots \;\; y_n]$. And the inequality now becomes: 

$$
\begin{split}
\boldsymbol{x}^TA\boldsymbol{x} &= \lambda_1y_1^2 + \lambda_2y_2^2 + \cdots + \lambda_ny_n^2 \\
&= \lambda_ky_k^2 + \cdots + \lambda_ny_n^ 2 \\
&\le \lambda_ky_k^2 + \cdots + \lambda_ky_n^2 \\ 
&\le \lambda_k(\boldsymbol{y}^T\boldsymbol{y}) \\
&= \lambda_k
\end{split}
$$

It's easy to see that $\boldsymbol{x}^TA\boldsymbol{x}$ gets its maximum $\lambda_k$ when $y_k = 0$ and other weights being zero. So the solution $\boldsymbol{x}$ can be solved as 

$$
\begin{split}
\boldsymbol{x} &= 
\begin{bmatrix}
\boldsymbol{q}_1 &  \cdots & \boldsymbol{q}_k &   \boldsymbol{q}_{k+1} & \cdots &\boldsymbol{q}_n
\end{bmatrix}
\begin{bmatrix}
0 \\
\vdots \\
\underbrace{1}_{k\text{th weight}} \\
0 \\
\vdots \\
0
\end{bmatrix} \\
&= \boldsymbol{q}_k
\end{split}
$$



## SVD   

### Singular values of m x n matrix

The singular value decomposition illustrates a way of decomposing *any* matrix $A \in \mathbb{R}^{m \times n}$ into the form $U \Sigma V^T$, where $U = [\boldsymbol{u}_1 \;\; \cdots \;\; \boldsymbol{u}_n]$ and $V = [\boldsymbol{v}_1 \;\; \cdots \;\; \boldsymbol{v}_n]$ are both orthogonal matrices, and $\Sigma$ a diagonal matrix with entries being the square root of the eigenvalues of $A^TA$ (perhaps plus some zeros).  

Before proceeding to the theorem, let's explore the motivating idea behind SVD. For (square) diagonalizable matrix $A \in \mathbb{S}^{n}$, the absolute value of the eigenvalues measure the amounts that $A$ stretches or shrinks eigenvectors, consider the ratio between the length of $\boldsymbol{x}$ before and after left multiplied by $A$ 

$$
\frac{||A\boldsymbol{x}||}{||\boldsymbol{x}||} 
= \frac{||\lambda\boldsymbol{x}||}{||\boldsymbol{x}||}
= \frac{\lambda||\boldsymbol{x}||}{||\boldsymbol{x}||} = \lambda
$$
If $\lambda_1$ is the greatest eigenvalue, then the corresponding eigenvector $\boldsymbol{v}_1$ identifies the direction in which $A$'s stretching effect is greatest. 

So, the question is, can we identify a similar ratio and direction for *rectangular* matrices $A \in \mathbb{R}^{m \times n}$, even though they does not have eigenvalues and eigenvectors?  

The answer is yes. Note that maximize $\frac{||A\boldsymbol{x}||}{||\boldsymbol{x}||}$ (now $\boldsymbol{x}$ is any vector $\in \mathbb{R}^n$) is equivalent to maximize $\frac{||A\boldsymbol{x}||^2}{||\boldsymbol{x}||^2}$ 

$$
\begin{split}
\frac{||A\boldsymbol{x}||^2}{||\boldsymbol{x}||^2} &= \frac{(A\boldsymbol{x})^T(A\boldsymbol{x})}{\boldsymbol{x}^T\boldsymbol{x}} \\
&= \frac{\boldsymbol{x}^T(A^TA)\boldsymbol{x}}{\boldsymbol{x}^T\boldsymbol{x}}
\end{split}
$$
Since $A^TA$ is **symmetric**, this is the form of a Rayleigh quotients \@ref(rayleigh-quotients)! We know that the largest possible value is of this quotient $\lambda_1$, the greatest eigenvalue of $A^TA$, with $\boldsymbol{x} = \boldsymbol{v}_1$, among the **orthonormal** set $\{\boldsymbol{v}_1, \cdots, \boldsymbol{v}_n\}$. Note that here $V = [\boldsymbol{v}_1 \;\; \cdots \;\; \boldsymbol{v}_n]$ is already a orthogonal matrix, previously denoted by $Q$. 

To sum up, the greatest possible stretching ratio of $A \in \mathbb{R}^{m \times n}$ on a vector $\boldsymbol{x} \in \mathbb{R}^n$ is $\sqrt{\lambda_1}$. Generally, let $\{\boldsymbol{v}_1, \cdots, \boldsymbol{v}_n\}$ be a orthonormal basis for $\mathbb{R}^n$ consisting of eigenvectors of $A^TA$, and $\lambda_1, ..., \lambda_n$ be the eigenvalues of $A^TA$, for $i = 1, \cdots, n$

$$
||A\boldsymbol{v}_i|| ^ 2 = \boldsymbol{v}_i^T(A^TA)\boldsymbol{v}_i = \lambda_i\boldsymbol{v}_i^T\boldsymbol{v}_i = \lambda_i
$$

<br>  

\BeginKnitrBlock{definition}\iffalse{-91-83-105-110-103-117-108-97-114-32-118-97-108-117-101-115-93-}\fi{}<div class="definition"><span class="definition" id="def:unnamed-chunk-14"><strong>(\#def:unnamed-chunk-14)  \iffalse (Singular values) \fi{} </strong></span>The **singular values** of $A$ are the square roots of the eigenvalues of $A^TA$, denoted by $\sigma_1, ..., \sigma_n$. That is,  $\sigma_i = \sqrt{\lambda_i}$, and they are often arranged in descending order so that $\lambda_1 \ge \cdots \ge \lambda_n$. Geometrically, singular values of $A$ are the lengths of the vectors $A\boldsymbol{v}_1, ..., A\boldsymbol{v}_n$, where $\{\boldsymbol{v}_1, ..., \boldsymbol{v}_n\}$ is the *orthonormal* basis of $A^TA$'s eigenspace. </div>\EndKnitrBlock{definition}


<br>

\BeginKnitrBlock{theorem}<div class="theorem"><span class="theorem" id="thm:svd-rank"><strong>(\#thm:svd-rank) </strong></span>Proceeding from previous definitons of singular values, and suppose $A$ has at least one nonzero singular values. Then $\{A\boldsymbol{v}_1, ..., A\boldsymbol{v}_r\}$ is an orthogonal basis for $\text{Col}\; A$, and $\text{rank} \;A = r$</div>\EndKnitrBlock{theorem}


**PROOF**  

First, let's examine that $\{A\boldsymbol{v}_1, ..., A\boldsymbol{v}_r\}$ is a orthogonal basis: any pair of two distinct vectors $A\boldsymbol{v}_i, A\boldsymbol{v}_j, \; i,j = 1, ..., r$ are orthogonal to each other 

$$
\begin{split}
(A\boldsymbol{v}_i)^T(A\boldsymbol{v}_j) &=  \boldsymbol{v}_i^TA^TA\boldsymbol{v}_j \\
&= \boldsymbol{v}_i^T(\lambda_j\boldsymbol{v}_j) \\
&= 0
\end{split}
$$

Next, we will show that any vector in $\text{Col}\; A$ is a linear a combination of $\{A\boldsymbol{v}_1, ..., A\boldsymbol{v}_r\}$. Note that $\{\boldsymbol{v}_1, ..., \boldsymbol{v}_r\}$ is a orthonormal basis of $A^TA$'s eigenspace $\mathbb{R}$. So for any vector $\boldsymbol{y} = A\boldsymbol{x}$ in $\text{Col}\; A$ , we can write $\boldsymbol{x} = c_1\boldsymbol{v}_1 + \cdots + c_n\boldsymbol{v}_n$, thus

$$
\begin{split}
\boldsymbol{y} &= A\boldsymbol{x} = A(c_1\boldsymbol{v}_1 + \cdots + c_n\boldsymbol{v}_n) \\
&= c_1 A \boldsymbol{v}_1 + \cdots + c_r A \boldsymbol{v}_r + c_{r+1} A \boldsymbol{v}_{r+1} + \cdots + c_n A \boldsymbol{v}_n 
\end{split}
\tag{1}
$$
Since $\lambda_{r+1} = \cdots = \lambda_{n} = 0$, $A\boldsymbol{v}_{r+1}, ..., A\boldsymbol{v}_{n}$ have length $0$: they are zero vectors. And (1) is reduced to 

$$
\boldsymbol{y} = c_1 A \boldsymbol{v}_1 + \cdots + c_r A\boldsymbol{v}_r
$$

Thus any $\boldsymbol{y} \in \text{Col}\; A$ is in Span$\{A\boldsymbol{v}_1, ..., A\boldsymbol{v}_r\}$, and $\{A\boldsymbol{v}_1, ..., A\boldsymbol{v}_r\}$ is an orthogonal basis for $\text{Col} \;A$. This also shows that the column rank of $A$ is equal to its number of nonzero singular values. 


### The singular value decomposition 

Let's begin SVD by the $m \times n$ diagonal matrix $\Sigma$ of the form 

$$
\Sigma = \begin{bmatrix}
\sigma_1 \\
& \ddots &  \\ 
& & \sigma_r \\
& & & 0 \\
& & & & \ddots \\
& & & & & 0 \\
\end{bmatrix}
\tag{1}
$$

There are $r$ nonzero entries on the diagonal, being $A$'s nonzero singular values, and the left positions are filled by $0$ to form a $m \times n$ matrix. If $r$ equals $m$ or $n$ or both, some or all of the zero blocks do not appear.  

\BeginKnitrBlock{theorem}\iffalse{-91-84-104-101-32-83-105-110-103-117-108-97-114-32-86-97-108-117-101-32-68-101-99-111-109-112-111-115-105-116-105-111-110-93-}\fi{}<div class="theorem"><span class="theorem" id="thm:SVD"><strong>(\#thm:SVD)  \iffalse (The Singular Value Decomposition) \fi{} </strong></span>Let $A \in \mathbb{R}^{m \times n}$ with rank $r$. There exists an diagonal matrix $\mathbb{\Sigma} \in \mathbb{R}^{m \times n}$ as in (1) for which the first $r\ \times r$ block is a diagonal matrix with the first $r$ singular values of $A$ on its diagonal, and there exist $U \in \mathbb{R}^{m \times m}$ and $V \in \mathbb{R}^{n \times n}$ such that 

$$
A = U \Sigma V^T
$$</div>\EndKnitrBlock{theorem}

**PROOF** 

Since $A$ has $r$ nonzero singular values which measure the length of $A\boldsymbol{v}_i, \; i = 1, ...n$, there exists orthogonal basis $\{A\boldsymbol{v}_1, ..., A\boldsymbol{v}_r\}$ for $\text{Col}$, we can further normalize the set to produce the *orthonormal* set $\boldsymbol{u}_1, ..., \boldsymbol{u}_r$: 

$$
\boldsymbol{u}_i = \frac{A\boldsymbol{v}_i}{\sigma_i}, \;\; i = 1, ..., r
$$
Now we can extend $\{\boldsymbol{u}_1, ..., \boldsymbol{u}_r\}$ to an orthonormal basis $\{\boldsymbol{u}_1, ..., \boldsymbol{u}_m\}$ of $\mathbb{R}^m$, and let 

$$
U = [\boldsymbol{u}_1 \;\; \cdots \;\; \boldsymbol{u}_m], \quad V = [\boldsymbol{v}_1 \;\; \cdots \;\; \boldsymbol{v}_n]
$$

and $\Sigma$ be as be as in (1) above. Write out

$$
\begin{split}
U\Sigma &= [\boldsymbol{u}_1 \;\; \cdots \;\; \boldsymbol{u}_r \;\; \cdots \;\; \boldsymbol{u}_m]_{m \times m}
\begin{bmatrix}
\sigma_1 \\
& \ddots &  \\ 
& & \sigma_r \\
& & & 0 \\
& & & & \ddots \\
& & & & & 0 \\
\end{bmatrix}_{m\times n} \\
&= [\sigma_1\boldsymbol{u}_1 \;\; \cdots \;\;   \sigma_r\boldsymbol{u}_r \;\; \boldsymbol{0} \;\;  \cdots \;\;  \boldsymbol{0}] \\
& = [A\boldsymbol{v}_1 \;\; \cdots \;\; A\boldsymbol{v}_r \;\; A\boldsymbol{v}_{r+1} \;\; \cdots \;\; A \boldsymbol{v}_n] \\
&= A_{m \times n}V_{n \times n}
\end{split}
$$

And because $V$ is orthogonal 

$$
A = U \Sigma V^{-1} =  U \Sigma V^{T}
$$
$\boldsymbol{u}_i$ and $\boldsymbol{v}_i$ are called *left eigenvector* and right eigenvector of $A$ respectively. 

It's easy to verify that the spectral decomposition \@ref(spectral-decomposition) is a special case of SVD when $A \in \mathbb{R}^{n}, \;\; m = n$. In that case, $\Sigma$ is a square matrix and $U$ is equal to $V$. 

When $\Sigma$ contains rows or columns of zeros (i.e, $r < \min(m, n)$), we can write SVD in a more compact form. Divide $U, \Sigma, V$ into submatrices

$$
U = [U_r \;\; U_{m-r}], \quad \text{where } U_r = [\boldsymbol{u}_1 \;\; \cdots \;\; \boldsymbol{u}_r] \\
V = [V_r \;\; V_{m-r}], \quad \text{where } V_r = [\boldsymbol{v}_1 \;\; \cdots \;\; \boldsymbol{v}_r] \\
\Sigma = 
\begin{bmatrix}
D & 0 \\
0 & 0
\end{bmatrix}
\quad \text{where } D = 
\begin{bmatrix}
\lambda_1 \\ 
 & \ddots \\
 & & \lambda_r
\end{bmatrix}
$$
The partitioned matrix multiplication shows that 

$$
A = [U_r \;\; U_{m-r}]
\begin{bmatrix}
D & 0 \\
0 & 0
\end{bmatrix}
\begin{bmatrix}
V_r^T \\
V_{n-r}^T
\end{bmatrix}
= U_rDV_{r}^T
$$
This more compact form is called a reduced **singular value decomposition**.  

Another way to write this is 

$$
A = \sum_{i=1}^{t}{\sigma_i}\boldsymbol{u}_i\boldsymbol{v}_i
$$

<hr> 

Right multiply the non-compact form $A = U\Sigma V^T$ by $A^T$  , we get the spectral decomposition of symmetric matrix $AA^T$.

$$
AA^T = (U \Sigma V^T)(U \Sigma V^T)^T = U \Sigma \Sigma^T VV^TU^T = U (\Sigma\Sigma^T) U^T       \tag{1}
$$

Therefore, $[\boldsymbol{u}_1 \;\; \cdots \;\; \boldsymbol{u}_n]$ are revealed as the orthonormal basis for $AA^T$'s eigenspace, as $[\boldsymbol{v}_1 \;\; \cdots \;\; \boldsymbol{v}_n]$ are for $A^TA$.   

(1) echoes the fact that $A^TA$ and $AA^T$ have the same set of nonzero eigenvalues, because $\Sigma\Sigma^T$ produces nonzero set $\lambda_1, ..., \lambda_r$.  

In fact, if were to ask for a direction in which $A^T$ has its greatest stretching effect instead of $A$, we would still result in the equivalent decomposition $A^T =  V\Sigma U^T$, with $\boldsymbol{v}_i = \frac{A\boldsymbol{u}_i}{\sigma_i}$. 

It's also easy to test that $\{A\boldsymbol{u}_1, ..., A\boldsymbol{u}_r\}$ produces an orthogonal basis for $\text{row}\; A$ or $\text{Col}\;A^T$. The process is analogous to theorem \@ref(thm:svd-rank) where $\{A\boldsymbol{v}_1, ..., A\boldsymbol{v}_r\}$ are shown to span $\text{Col}\; A$. 

For any vector $\boldsymbol{y}$ in $\text{Col}\;A^T$, we have 




$$
\begin{align*}
\boldsymbol{y} &= A^T\boldsymbol{x} \\
&= A^T(c_1\boldsymbol{u}_1 + \cdots + c_1\boldsymbol{u}_n) \\
&= c_1A\boldsymbol{u}_1 + \cdots + c_rA\boldsymbol{u}_r + \boldsymbol{0} + \cdots + \boldsymbol{0} && (\text{because }A\boldsymbol{u}_i = \sigma_i\boldsymbol{v}_i)\\
&= c_1A\boldsymbol{u}_1 + \cdots + c_rA\boldsymbol{u}_r 
\end{align*}
$$



### The condition number


### Low-rank approximation 