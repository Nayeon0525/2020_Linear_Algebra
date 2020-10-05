# Chapter 01. Linear Equations in Linear Algebra
--------------------------------------------------
## 1.1 Systems of Linear Equations
### 1.1.1 linear equation이란
$a_{1}x_{1} + a_{2}x_{2}+...+a_{n}x_{n}=b$
> $b$ 와 coefficient "$a_{1}...a_{n}$"는 real 또는 complex number 이다.

> *Warning*  
> $4x_{1} - 5x_{2} = x_{1}x_{2}$ 는 linear하지 않다.
> 
### 1.1.2 system of linear equations(or linear system)이란  
* 하나 또는 하나 이상의 linear equation의 모음.
    * EX) $2x_{1} - x_{2} + 1.5x_{3} =  8$  
        $x_{1} - 5x_{2} + 2x_{3} =  -7$  
        
### 1.1.3 solution of linear system  
> 1. no solution
> 2. exactly one solution
> 3. infinitely many solutions

### 1.1.4 Matrix Notation
* **linear system**
> $x_{1} -2x_{2} +  x_{3} = 0$  
> $       2x_{2} - 8x_{3} = 8$  
> $5x_{1} -5x_{3} = 10$

* **coefiicient matrix(or matrix of coefficients)**  
> $\begin{bmatrix} 1 & -2 & 1 \\ 0 & 2 & -8 \\ 5 & 0 & -5 \end{bmatrix}$

* **augmented matrix**   
> $\begin{bmatrix} 1 & -2 & 1 & 0 \\ 0 & 2 & -8 & 8\\ 5 & 0 & -5 & 10\end{bmatrix}$

### 1.1.5 Solving a Linear System
> **Elementary Row Operations**
> 1. Replacement
> 2. Interchange
> 3. Scaling

### 1.1.6 Existence and Uniqueness Questions
> **linear system에 대한 두가지 질문**
> 1. Is the system **consistent** : that is, does at least one solution *exist*? (one solution or infinitely many solution)
> 2. If a solution **exists**, is the *only one* : that is , is the solution *unique*?
![solutionset](https://user-images.githubusercontent.com/53852102/95113427-68790480-077d-11eb-9fab-5d2c5c93f6ab.png)


----------------------------
## 1.2 Row Reduction and Echelon Form

### *Definition* : echelon form
> a rectangular matrix가 **echelon form(또는 row echelon form)** 이면 아래와 같은 특성을 따른다.  
> 1. 모든 nonzero row는 zero 행 위에 있다.
> 2. 각 행의 leading entry는 그 위의 leading entry에 비해 오른쪽에 위치한다.
> 3. leading entry 밑에 있는 columndm은 모두 zero이다.
> **reduced echelon form (or reduced row echelon form, RREF)** 일 때는
> 4. leading entry 가 1이다. (; leading 1)  
> 5. leading 1을 포함하는 각 열은 leading 1의 위아래가 0이어야 한다.
* row-reduced란 elementary row operations에 의해 변환된 것

### *Theorem 1* : Uniqueness of the Reduced Echelon Form
> reduced chelon matrix는 유일무이하다. (row equivalent)

### *Definition* : pivot position
> reduced echelon form matrix에서 leading 1과 상응하는 위치, pivot position을 포함하는 column을 pivot coloum이라고 한다.

### *Theorem 2* : Existence and Uniqueness Theorem 
> linear system이 consitent하다면,   
> (i) **unique solution** (no free variable)  
> (ii) **infinitely many solutions** (at least one free variable)

**EX)**  
* linear system  
$3x_{2} - 6x_{3} + 6x_{4} + 4x_{5} = -5$  
$3x_{1} - 7x_{2} - 8x_{3} - 5x_{4} + 8x_{5} = 9$  
$3x_{1} - 9x_{2} + 12x_{3} - 9x_{4} + 6x_{5} = 15$

* augmented matrix  
$\begin{bmatrix} 0 & 3 & -6 & 6 & 4 & -5 \\ 3 & -7 & -8 & -5 & 8 & 9 \\ 3 & -9 & 12 & -9 & 6 & 15\end{bmatrix}\sim \begin{bmatrix} 3 & -9 & 12 & -9 & 6 & 15 \\ 0 & 2 & -4 & 4 & 2 & -6 \\ 0 & 0 & 0 & 0 & 1 & 4 \end{bmatrix}$

> basic variables : $x_{1}, x_{2}, x_{5}$  
> free variables :  $x_{3}, x_{4}$  
> 따라서 이 solution은 free variable이 어떤 값을 가지냐에 따라 달라지므로 *unique하지 않다.*

-----------------------------
## 1.3 Vector Equations
### 1.3.1 Vectors in $\mathbb{R}^n$
* n x 1 column matrices with n entries.
* represented geometrically by points in a n-dimensional coordinate space
* Two vectors in $\mathbb{R}^n$ are equal if and only if their corresponding etries are equal (because vectors are ordered pairs of real numbers.)

> **EX)**  
> vector **u**, **v** in $\mathbb{R}^2$ (즉, n=2)
> vectos with two entries  
> **u** = $\begin{bmatrix} 3 \\ -1 \end{bmatrix}$, **v** = $\begin{bmatrix} .2 \\ .3 \end{bmatrix}$

> #### Algebraic Properties of $\mathbb{R}^n$
> for all **u, v, w** in $\mathbb{R}^n$ and all scalars *c* and *d*:
> 1. **u** + **v** = **v** + **u** 
> 2. (**u** + **v**) + **w** = **u** + (**v** + **w**)
> 3. **u** + **0** = **0** + **u** = **u** 
> 4. **u** + (-**u**) = (-**u**) + **u** = **0**, where -**u** denotes (-1)**u** 
> 5. *c*(**u** + **v**) = *c* **u** + *c* **v** 
> 6. (*c* + *d*)**u** = *c* **u** + *d* **u** 
> 7. *c*(*d* **u**) = (*cd*)**u** 
> 8. 1**u** = **u** 

### *Definition* : linear combinations
> if $\mathbf{v_{1}}, \dots, \mathbf{v_{n}}$ are in $\mathbb{R}^n$,  
the set of all linear combinations of $\mathbf{v_{1}}, \dots, \mathbf{v_{n}}$은 Span{$\mathbf{v_{1}}, \dots, \mathbf{v_{n}}$}과 동일하다.
> 즉, Span{$\mathbf{v_{1}}, \dots, \mathbf{v_{n}}$}은 벡터들의 모임이며 $c_{1}\mathbf{v_{1}} + \dots + c_{p}\mathbf{v_{p}}$ (c는 스칼라)로 표현가능하다.

> **같은 표현**
> * vector equation  
> $x_{1}\mathbf{a_{1}} + x_{2}\mathbf{a_{2}} + \dots + x_{n}\mathbf{a_{n}} = \mathbf{b}$  
> * augmented matrix  
$\begin{bmatrix} \mathbf{a_{1}} & \mathbf{a_{2}} & \dots & \mathbf{a_{n}} & \mathbf{b} \end{bmatrix}$

### 1.3.2 A Geometric Description of Span{$\mathbf{v}$} and Span{$\mathbf{u, v}$}
어떤 벡터가 Span한다는 것은 벡터들의 가능한 모든 linear combination으로 공간을 형성하는 것을 의미, 형성되는 공간은 조합되는 벡터에 따라 $\mathbb{R}^n$, 또는 subspace가 될 수도 있다.

-----------------------------
## 1.4 The Matrix Equation $A\mathbf{x} = \mathbf{b}$
### *Definition* : $A\mathbf{x}$
> $A\mathbf{x} =$ $\begin{bmatrix} \mathbf{a_{1}} & \mathbf{a_{2}} & \dots & \mathbf{a_{n}} \end{bmatrix}$ $\begin{bmatrix} x_{1} \\ \dots \\ x_{n} \end{bmatrix}$ $= x_{1}\mathbf{a_{1}} + \dots + x_{n}\mathbf{a_{n}}$
> * $A$ : m x n matrix with columns $\mathbf{a_{1}}, \dots, \mathbf{a_{n}} $
> * $x$ : weights

### *Theorem 3* 
* $A$ : m x n matrix with columns $\mathbf{a_{1}}, \dots, \mathbf{a_{n}} $
* $\mathbf{b}$ : in $\mathbb{R}^n$
> * matrix equation
> $A\mathbf{x} = \mathbf{b}$
> * vector equation
> $x_{1}\mathbf{a_{1}} + \dots + x_{n}\mathbf{a_{n}}$
> * augmented matrix
> $\begin{bmatrix} \mathbf{a_{1}} & \mathbf{a_{2}} & \dots & \mathbf{a_{n}} & \mathbf{b} \end{bmatrix}$

### *Theorem 4* : Existence of Solutions 
> 아래 네 문장은 모두 동일한 의미이다.
> 1. $\mathbb{R}^n$에서 각 $\mathbf{b}$에 대해, $A\mathbf{x} = \mathbf{b}$는 solution을 가지고 있다.
> 2. $\mathbb{R}^n$에서 각 $\mathbf{b}$는 $A$의 column들의 linear combination이다.
> 3.  $A$의 column들은  $\mathbb{R}^n$을 span한다.
> 4. $A$는 모든 row에서 pivot position을 갖는다.
> * *Warning* : coefiicient matrix에서 해당한다.

### *Theorem 5* : Properies of the Matrix-Vector or Product $A\mathbf{x}$ 
> $A$는 m x n matrix, **u, v** vectors in $\mathbb{R}^n$, $c$는 scalar
> 1. $A(\mathbf{u} + \mathbf{v}) = A\mathbf{u} + A\mathbf{v}$
> 2. $A(c\mathbf{u}) = c(A\mathbf{u})$

---------------------------------------
## 1.5 Solution Sets of Linear Systems
### 1.5.1 Homogeneous Linear Systems, $A\mathbf{x} = \mathbf{0}$
* $A\mathbf{x} = \mathbf{0}$
* 항상 적어도 하나의 solution을 갖는다. $\mathbf{x}=\mathbf{0}$
* 위의 zero solution은 trivial solution이다. (;필요없는)
* 적어도 하나 이상의 free variable을 가질 때 non-trivial solution이다. 
> EX)  
> $3x_{1} + 5x_{2} - 4x_{3} = 0$  
> $-3x_{1} - 2x_{2} - 8x_{3} = 0$  
> $6x_{1} + x_{2} - 8x_{3} = 0$  
> $\begin{bmatrix} 3 & 5 & -4 & 0 \\ -3 & -2 & -8 & 0 \\ 6 & 1 & -8 & 0\end{bmatrix}$ **~** $\begin{bmatrix} 3 & 5 & -4 & 0 \\ 0 & 3 & 0 & 0 \\ 0 & -9 & 0 & 0\end{bmatrix}$ **~** $\begin{bmatrix} 3 & 5 & -4 & 0 \\ 0 & 3 & 0 & 0 \\ 0 & 0 & 0 & 0\end{bmatrix}$ **~** $\begin{bmatrix} 1 & 0 & -4/3 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 0\end{bmatrix}$  
> * $x_{1} - 4/3x_{3} = 0$
> * $x_{2} = 0$
> * 0 = 0   
> $\mathbf{x} = \begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \end{bmatrix} = \begin{bmatrix} 4/3x_{3} \\ 0 \\ x_{3} \end{bmatrix} = x_{3}\begin{bmatrix} 4/3 \\ 0 \\ 1 \end{bmatrix} = x_{3}\mathbf{v}$, where $\mathbf{v}=\begin{bmatrix} 4/3 \\ 0 \\ 1 \end{bmatrix}$
> * **따라서 free variable인 $x_{3}$이 nontrivial 하다.**

### 1.5.2 Parametric Vector Form
$\mathbf{x} = s\mathbf{u} + t\mathbf{v}$

### 1.5.3 Solutions of Nonhomogeneous Systems, $A\mathbf{x} = \mathbf{b}$
> EX)  
> $A = \begin{bmatrix} 3 & 5 & -4 \\ -3 & -2 & 4 \\ 6 & 1 & -8\end{bmatrix}$ and $\mathbf{b} = \begin{bmatrix} 7 \\ -1 \\ -4 \end{bmatrix}$  
> $\begin{bmatrix} A & \mathbf{b} \end{bmatrix} = \begin{bmatrix} 3 & 5 & -4 & 7 \\ -3 & -2 & 4 & -1 \\ 6 & 1 & -8 & -4\end{bmatrix}$ **~** $\begin{bmatrix} 1 & 0 & -4/3 & -1 \\ 0 & 1 & 0 & 2 \\ 0 & 0 & 0 & 0\end{bmatrix}$  
> * $x_{1} - 4/3x_{3} = -1$
> * $x_{2} = 2$
> * 0 = 0   
> $\mathbf{x} = \begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \end{bmatrix} = \begin{bmatrix} -1 + 4/3x_{3} \\ 2 \\ x_{3} \end{bmatrix} = \begin{bmatrix} -1 \\ 2 \\ 0 \end{bmatrix} + \begin{bmatrix} 4/3x_{3} \\ 0 \\ x_{3} \end{bmatrix} = \begin{bmatrix} -1 \\ 2 \\ 0 \end{bmatrix} + x_{3}\begin{bmatrix} 4/3 \\ 0 \\ 1 \end{bmatrix}$   
> ,$\mathbf{x} = \mathbf{p} + x_{3}\mathbf{v}$

![figure3](https://user-images.githubusercontent.com/53852102/95114622-31a3ee00-077f-11eb-99a4-3c286bf52961.png)
![figure5](https://user-images.githubusercontent.com/53852102/95114663-3e284680-077f-11eb-845a-5fd22cd10bf6.png)

> #### Parallel solution sets of $A\mathbf{x} = \mathbf{b}$ and $A\mathbf{x} = \mathbf{0}$  
> 즉, $A\mathbf{x} = \mathbf{b}$의 solution은 $A\mathbf{x} = \mathbf{0}$의 solution에 $\mathbf{p}$를 더함으로써 얻을 수 있다.


### *Theorem 6* 
> Suppose the equation $A\mathbf{x} = \mathbf{b}$ is consistent for some given $\mathbf{b}$, and let $\mathbf{p}$ be a solution. Then the solution set of  $A\mathbf{x} = \mathbf{b}$ is the set of all vectors of the form $\mathbf{w} = \mathbf{p} + \mathbf{v_{h}}$, where $\mathbf{v_{p}}$ is solution of the homogeneous equation $A\mathbf{x} = \mathbf{0}$. 

------------------------------------
## 1.7 Linear Independence
### *Definition* : linearly independece & dependence
> indexed set of vectors ${\mathbf{v_{1}}, \dots, \mathbf{v_{p}}}$ in $\mathbb{R}^n$ 
> 1. linearly independent  
> vector equation $x_{1}\mathbf{v_{1}} + x_{2}\mathbf{v_{2}} + \dots + x_{p}\mathbf{v_{p}} = \mathbf{0}$가 오직 **trivial solution**만 갖는다면 ${\mathbf{v_{1}}, \dots, \mathbf{v_{p}}}$는 Linearly independent하다.
> 2. linearly dependent  
> vector equation $c_{1}\mathbf{v_{1}} + c_{2}\mathbf{v_{2}} + \dots + c_{p}\mathbf{v_{p}} = \mathbf{0}$에서 weight c가 모두 0이 아니면 ${\mathbf{v_{1}}, \dots, \mathbf{v_{p}}}$는 Linearly dependent하다.  

> **EX)  set ${\mathbf{v_{1}, v_{2}, v_{3}}}$이 linearly independent한가?**  
> $\mathbf{v_{1}} = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$, $\mathbf{v_{2}} = \begin{bmatrix} 4 \\ 5 \\ 6 \end{bmatrix}$, $\mathbf{v_{3}} = \begin{bmatrix} 2 \\ 1 \\ 0 \end{bmatrix}$  
> sol)    
> $\begin{bmatrix} 1&4&2&0 \\ 2&5&1&0 \\ 3&6&0&0 \end{bmatrix}$ **~** $\begin{bmatrix} 1&0&-2&0 \\ 0&1&1&0 \\ 0&0&0&0 \end{bmatrix}$  
> * basic variable : $x_{1}, x_{2}$ (= trivial variable)  
> * free variable : $x_{3}$ (= nontrvial variable)   
> * 즉, nontrvial variable이 존재하므로 set ${\mathbf{v_{1}, v_{2}, v_{3}}}$은 linearly dependent하다. 

### 1.7.1 Sets of One or Two Vectors
![linearly_dependent](https://user-images.githubusercontent.com/53852102/95114754-60ba5f80-077f-11eb-8308-e0df10605139.png)
> * **위** : $\mathbf{v_{1}} = \begin{bmatrix} 3 \\ 1 \end{bmatrix}$, $\mathbf{v_{2}} = \begin{bmatrix} 6 \\ 2\end{bmatrix}$  
> $\mathbf{v_{2}} = 2\mathbf{v_{1}}$, 즉 scalar multiple로 만들어 낼 수 있다. --> linearly dependent  
> * **아래** : $\mathbf{v_{1}} = \begin{bmatrix} 3 \\ 2 \end{bmatrix}$, $\mathbf{v_{2}} = \begin{bmatrix} 6 \\ 2\end{bmatrix}$    
> scalar multiple로 만들어 낼 수 없다. --> linearly independent

  
### 1.7.2 Sets of Two or More Vectors
### *Theorem 7* : Characterization of Linearly Dependent Sets 
> set $S =${$\mathbf{v_{1}}, \dots, \mathbf{v_{p}}$}의 둘 또는 그 이상의 벡터가 linearly dependent하다면 set $S$의 벡터로 다른 벡터를 linear combination으로 표현 가능하다. 

**EX) $\mathbf{u} = \begin{bmatrix} 3\\1\\0 \end{bmatrix}$, $\mathbf{v} = \begin{bmatrix} 1\\6\\0 \end{bmatrix}$가 주어졌다. {$\mathbf{u, v, w}$}가 linearly dependent할 때, Span{$\mathbf{u, v}$}에서 벡터 $\mathbf{w}$가 dependent한지 independent한지 설명하라.**  
> **Sol)**  
> {$\mathbf{u, v, w}$}가 linearly dependent하다는 것은 
    > * Span{$\mathbf{u, v}$}와 Span{$\mathbf{u, v, w}$}이 동일
    > * $\mathbf{w}$가 $\mathbf{u}$, $\mathbf{v}$의 linear combination으로 형성 가능
    > * $\mathbf{w}$가 Span{$\mathbf{u, v}$}에 속해있다.  
> 는 뜻이다.  따라서 Span{$\mathbf{u, v}$}에서 벡터 $\mathbf{w}$가 dependent하다.

> ![theorem7](https://user-images.githubusercontent.com/53852102/95114800-72036c00-077f-11eb-900a-2164df860d3c.png)



### *Theorem 8*
> $p>n$일 때, set {$\mathbf{v_{1}}, \dots, \mathbf{v_{p}}$} in $\mathbb{R}^n$은 lineearly dependent하다.

### *Theorem 9*
> set $S =${$\mathbf{v_{1}}, \dots, \mathbf{v_{p}}$} in $\mathbb{R}^n$이 zero vector를 포함하고 있다면 그 set은 linearly dependent하다.

--------------------------------
## 1.8 Introduction to Linear Transformations
### 1.8.1 Linear Transformations
#### A transformation(or function or mapping) $T$ from  $\mathbb{R}^n$ to  $\mathbb{R}^m$ is a rule that assigns to each vector $\mathbf{x}$ in  $\mathbb{R}^n$ a vector $T(\mathbf{x})$ in  $\mathbb{R}^m$
* $T$ is m x n
* set $\mathbb{R}^n$ : **domain** of $T$ ; 정의역
* set $\mathbb{R}^m$ : **codomain** of $T$ ; 공역
* set of all images $T(\mathbf{x})$ : **range** of $T$  
![linear_transformation](https://user-images.githubusercontent.com/53852102/95114849-88a9c300-077f-11eb-80f6-457b423c8f6a.png)

### *Definition*
> A transformation(or mapping) $T$ is linear if:  
> 1. $T(\mathbf{u + v}) = T(\mathbf{u}) + T(\mathbf{v})$ for all $\mathbf{u, v}$ in the domain of $T$. ; additivity  
> 2. $T(c\mathbf{u}) = cT(\mathbf{u})$ for all scalars $c$ an all $\mathbf{u}$ in the domain of $T$. ; homogeneity
    > * following useful facts
    > 3. $T(\mathbf{0}) = \mathbf{0}$  
    > 2에 의해 $T(\mathbf{0}) = T(0\mathbf{u}) = 0T(\mathbf{u}) = \mathbf{0}$
    > 4. $T(c\mathbf{u} + d(\mathbf{v}) = cT(\mathbf{u}) + dT(\mathbf{v})$  
    > 1과 2에 의해 $T(c\mathbf{u} + d(\mathbf{v}) = T(c\mathbf{u}) + T(d\mathbf{v}) = cT(\mathbf{u}) + dT(\mathbf{v})$
    
* **superposition principle**  
$T(c_{1}\mathbf{v_{1}} + \dots + c_{p}\mathbf{v_{p}}) = c_{1}T(\mathbf{v_{1}}) + \dots +  c_{p}T(\mathbf{v_{p}})$  
The system satisfies the superposition principle if whenever an input is expressed as a linear combination of such signals, the system's response is the same linear combination of the responses to the individual signals.


-----------------------
## 1.9 The Matrix of a Linear Transformation

### *Theorem 10*
> Let $T : \mathbb{R}^n {\rightarrow} \mathbb{R}^m$ be a linear transformation. Then there **exists a unique matrix** $A$ such that  
$$T(\mathbf{x}) = A\mathbf{x}$$ for all $\mathbf{x}$ in $\mathbb{R}^n$  
In fact, $A$ is the $m * n$ matrix whose $j$th column is the vector $T(\mathbf{e_{j}})$, where $\mathbf{e_{j}}$ is the $j$th column of the identity matrix in $\mathbb{R}^n$:  
$$A = \begin{bmatrix} T(\mathbf{e_{1}}) & \dots & T(\mathbf{e_{j}}) \end{bmatrix}$$ (; $A$ = **standard matrix for the linear transformation $T$**)


### *Definition* : onto
> A mapping $T : \mathbb{R}^n {\rightarrow} \mathbb{R}^m$ is said to be **onto** $\mathbb{R}^m$ if each **b** in $\mathbb{R}^m$ is the image of at least one $\mathbf{x}$ in $\mathbb{R}^n$  
![onto](https://user-images.githubusercontent.com/53852102/95114915-9eb78380-077f-11eb-93b9-d0ca4af902d7.png)


### *Definition* : one-to-one
> A mapping $T : \mathbb{R}^n {\rightarrow} \mathbb{R}^m$ is said to be **one-to-one** if each **b** in $\mathbb{R}^m$ is the image of at most one $\mathbf{x}$ in $\mathbb{R}^n$  
![one-to-one](https://user-images.githubusercontent.com/53852102/95114953-ae36cc80-077f-11eb-8fb4-7607d44bf909.png)


### *Theorem 11*
> Let $T : \mathbb{R}^n {\rightarrow} \mathbb{R}^m$ be a linear transformation. Then $T$ is one-to-one if and only if the equation  $T(\mathbf{x}) = \mathbf{0}$ has **only trivial solution.**


### *Theorem 12*
> Let $T : \mathbb{R}^n {\rightarrow} \mathbb{R}^m$ be a linear transformation. and let $A$ be the standard matrix for $T$. then:  
a. $T$ maps $\mathbb{R}^n$ onto $\mathbb{R}^m$ if and only if the columns of $A$ span $\mathbb{R}^m$  
b. $T$ is one-to-one if and only if the columns of $A$ are linearly independent.


```python

```
