---
layout: post
title: "An Example in LaTeX"
date: 2026-09-10
---
The Harnack inequality, in its classical form, provides a way to compare the values of the positive solution at different points. In their 1986 seminal paper, Peter Li and Shing-Tung Yau introduced a revolutionary differential form of the Harnack inequality for the heat equation on Riemannian manifolds, now known as the Li-Yau Harnack inequality.

This differential inequality is very important in geometric analysis and they crop up in Hamilton's analysis of the Ricci flow on surfaces as well. 

In this expository article, we explore the Li-Yau Harnack inequality in three increasingly general settings. We begin with the simplest case of closed manifolds, where the absence of boundary terms makes the analysis easy. We then examine the more delicate case of Euclidean domains, where we perform a more careful analysis through cut-off functions. Finally, we extend our investigation to complete noncompact manifolds. A reference for all this is the original paper of Li-Yau. We will mention Hamilton's generalization of Li-Yau Harnack inequality at the end.  

## Harnack inequality on closed manifolds

We will begin by the easiest case: on a closed manifold, the reason being that we don't have to worry about the boundary. The Li-Yau Harnack inequality takes the following form. 
<div class="theorem" id="theorem-1">

Let \(M^n\) be a closed (i.e. compact without boundary) \(n\)-dimensional Riemannian manifold with non-negative Ricci curvature, i.e. \(\operatorname{Ric}_g \geq 0\). Let \(u: M \times[0, \infty) \rightarrow\) \([0, \infty)\) be a non-negative smooth solution to the heat equation:
$$
\partial_t u(x, t)=\Delta_g u(x,t), \quad x \in M, t \in[0, T] .
$$
The following holds: \(M \times(0, \infty)\), 
$$\partial_t \log u- |\nabla \log u|^2+\frac{n}{2t}\geq 0$$
</div>
Note that the inequality becomes equality \(M=\mathbb{R}^n\) with the flat metric and \(u\) is given by 
$$
u(x, t)=\frac{1}{(4 \pi t)^{n / 2}} e^{-\frac{\mid x|^2}{4 t}}
$$
<div class="proof">

<span class="proof-title">Proof.</span>

**Step 1. Decide your quantity.** One first sees that 
$$P:=\partial_t \log u- |\nabla \log u|^2=\frac{\Delta u}{u}-\frac{|\nabla u|^2}{u^2}=\Delta \log u$$
The last equality is a quick computation: 
$$\nabla^2 \log u=\nabla (\frac{\nabla u}{u})=\frac{1}{u}\nabla^2 u-\frac{\nabla u\otimes \nabla u}{u^2}$$
**Step 2. Compute its variation and get a favorable inequality.** The idea of making this transformation is that one can now compute its variation and we want to get an equation as \(\partial_t P=\Delta P+\)some other terms possibly involving \(P\). Because time and space derivatives commute, we have 
$$\frac{\partial}{\partial t}(\Delta \log u) =\Delta\left(\frac{\partial}{\partial t} \log u\right)=\Delta(\frac{\Delta u}{u})=\Delta\left(\Delta \log u+|\nabla \log u|^2\right) $$
To take care of the second term, we need to commute \(\Delta\) and \(\nabla\). This is the so called "Bochner formulae" which follows form commutation of derivatives.
$$\Delta(\nabla_i f)=\nabla_i (\Delta f)+R_{i}^j\nabla_j f$$
We obtain: 
$$\nabla^2 |\nabla f|^2 =2\langle \nabla(\nabla f),\nabla(\nabla f)\rangle+2\langle \nabla^2 (\nabla f),\nabla f\rangle$$
which shows 
$$\Delta |\nabla f|^2=2|\nabla^2 f|^2+2\langle \Delta(\nabla f),\nabla f\rangle$$
and using Bochner, 
$$\Delta|\nabla f|^2=2|\nabla^2 f|^2+2\langle \nabla (\Delta f),\nabla f\rangle+2\operatorname{Ric}(\nabla f,\nabla f)$$
Returning to \(P\), we have 
$$\partial_t P=\Delta P+2|\nabla^2 \log u|^2+2\langle \nabla P,\nabla \log u\rangle +2\operatorname{Ric}(\nabla \log u,\nabla \log u)$$
We can drop the \(\operatorname{Ric}\) term and use Cauchy-Schwars on the square term and we will still be going in the right direction to obtain 
$$\partial_t P\geq \Delta P+2\langle \nabla P,\nabla \log u\rangle +\frac{2}{n}P^2$$
**Step 3. Apply the WEAK Maximum principle.** We are in the right position to apply maximum principle! The final step 
$$\begin{aligned}
\partial_t (P+\frac{n}{2t})&\geq \Delta (P+\frac{n}{2t})+2\langle \nabla (P+\frac{n}{2t}),\nabla \log u\rangle \\
&+\frac{2}{n}(P+\frac{n}{2t})^2-\frac{2}{t}(P+\frac{n}{2t})
\end{aligned}$$
We have obtained a parabolic inequality for our desired quantity. To obtain a contradiction assume that \(\inf_{M\times (0,T]} (P+\frac{n}{2t})<0\). Because \(M\) is compact and our quantity blows up as \(t\to 0\), this minima is actually attained, say at \((x_0,t_0)\). Then at \((x_0,t_0)\), looking at the inequality above, we see 
$$0\geq -\frac{2}{t_0}(P(x_0,t_0)+\frac{n}{2t_0})$$
which is a contradiction. The theorem is proved. 



<span class="qed">∎</span>

</div>



The inequality hints that a similar inequality is possible for Ricci flow on a closed surface. Let \((M^2,g(t))\) be a solution to the Ricci flow on a surface with \(R>0\), i.e. 
$$\partial_t g=-Rg$$
Then one computes for the scalar curvature \(R_g\) that 
$$\partial_t R=\Delta R+R^2 $$
Thus one may expect a Harnack inequality in this case as well. This was confirmed by Hamilton. <div class="theorem" id="theorem-2">
<strong>Hamilton-trace differential Harnack on surfaces.</strong> 
The trace Harnack quantity is defined by
$$
Q=\Delta \log R+R+\frac{1}{t}=\frac{\partial}{\partial t} \log R-|\nabla \log R|^2+\frac{1}{t}
$$
Then, 
$$
Q(x, t) \geq 0
$$
for all \(x \in M^2\) and \(t>0\). 
</div>
Notice the remarkable similarity with the heat equation! The proof of this theorem proceeds in the same way as the previous theorem and we shall not carry it out here. See B. Chow's book for more details. 


## The Harnack inequality on complete noncompact manifolds
Let us now think about a differential Harnack inequality on a ball in \(\mathbb{R}^n\). The main difference from this situation and a closed manifold is that we need to worry about the boundary. We have the following differential Harnack inequality for arbitrary positive solutions of the heat equation. 
<div class="theorem" id="theorem-3">

Suppose \(u \in C^{2,1}\left(B_1 \times(0,1]\right)\) satisfies
$$
u_t-\Delta u=0, u>0 \quad \text { in } B_1 \times(0,1]
$$
Then for any \(\alpha \in(0,1), v=\log u\) satisfies
$$
\partial_t v-\alpha|\nabla v|^2+\frac{n}{2 \alpha t}+C \geq 0 \quad \text { in } B_{1 / 2} \times(0,1]
$$
where \(C\) is a positive constant depending only on \(n\) and \(\alpha\). 
</div>
For a different proof than the one given below, see Qing Han's book, or Reto Müller's book.
<div class="proof">

<span class="proof-title">Proof.</span>

**Step 1. Decide your quantity.** Firstly we may assume \(u\) is continuous on \(B_1\times [0,1]\) for otherwise, carry out the proof on \(B_1\times [\varepsilon,1]\) and take \(\varepsilon\to 0\). Recall the identity
$$\Delta \log u=\frac{\Delta u}{u}-|\nabla \log u|^2$$
From here we derive that the Harnack quantity is: 
$$\partial_t v-|\nabla v|^2=\Delta v$$
$$\partial_t v-\alpha|\nabla v|^2+\frac{n}{2 \alpha t}=\Delta v +(1-\alpha)|\nabla v|^2+\frac{n}{2\alpha t}$$
which means \(w:=\Delta v=\Delta \log u\) is the quantity to inverstigate now. One can compute in tensorial notation, 
$$\begin{aligned} \frac{\partial}{\partial t}(\Delta \log u) & =\Delta\left(\frac{\partial}{\partial t} \log u\right)=\Delta\left(\Delta \log u+|\nabla \log u|^2\right) \\ & =\Delta(\Delta \log u)+2 \nabla \log u \cdot \Delta \nabla \log u+2|\nabla \nabla \log u|^2 \\ 
& \underset{(*)}{=}\Delta(\Delta \log u)+2 \nabla \log u \cdot \nabla \Delta \log u+2|\nabla \nabla \log u|^2 \end{aligned}$$
So we have 
$$\partial_t w= \Delta w+2\langle\nabla v, \nabla w\rangle+2|\nabla^2 v|^2$$
Let us set 
$$S:=\Delta v+(1-\alpha)|\nabla v|^2$$
And we compute the variation of this quantity. Now we have 
$$\begin{aligned}
&\partial_t |\nabla v|^2=2\langle\nabla (\partial_t v),\nabla v\rangle\\
&=2\langle \nabla (\Delta v)+\nabla |\nabla v|^2,\nabla v\rangle\\
&\underset{(*)}{=}2\langle \Delta (\nabla v),\nabla v\rangle+2\langle \nabla |\nabla v|^2,\nabla v\rangle\\
&=2[\frac{1}{2}\Delta |\nabla v|^2-|\nabla^2 v|^2]+2\langle\nabla |\nabla v|^2,\nabla v\rangle
\end{aligned}$$

From this we obtain 
$$\partial_t S=\Delta S+2\alpha |\nabla^2 v|^2+2\langle \nabla v,\nabla S\rangle$$
In order to stay away from the boundary of \(B_1\), we need to use a cut-off function. Let \(\eta\in C_c^\infty(B_1)\) such that \(\eta\equiv 1\) on \(B_{1/2}\) and \(\eta:\mathbb{R}^n\to [0,1]\). Now we set 
$$H=t\eta^2 S$$
and start our long computation
$$\begin{aligned}
\partial_t H&=\eta^2 S+\eta^2 t(\Delta S+2\alpha |\nabla^2 v|^2+2\langle \nabla v,\nabla S\rangle)
\end{aligned}$$
while 
$$\Delta H=t(2\eta \Delta \eta S+2|\nabla \eta|^2S+\eta^2 \Delta S)$$
$$\nabla H=tS(2\eta\nabla \eta)+t\eta^2 \nabla S$$
giving us 
$$\begin{aligned}
\partial_t H&=\eta^2 S+\Delta H-2\eta t\Delta \eta S-2|\nabla \eta|^2 S\\
&+\eta^2 t(2\alpha |\nabla^2 v|^2)+2\langle \nabla v,\nabla H-2tS\eta \nabla \eta\rangle
\end{aligned}$$
Cleaning it up we end up at  
$$\begin{aligned}
\partial_t H&=\Delta H+2\langle\nabla v,\nabla H\rangle+\frac{H}{t}-2H\frac{\Delta \eta }{\eta}\\
&-2|\nabla \eta|^2 \frac{H}{t\eta^2}-4\frac{H}{\eta} \langle \nabla v,\nabla \eta\rangle\\
&+\eta^2 t(2\alpha |\nabla^2 v|^2)
\end{aligned}$$
It is still not very clear whether we are ready to apply maximum principle simply because there are many terms with mixed sign. Remember we need to bring more positive terms on the right hand side. We can arrive at 
$$\begin{aligned}
\partial_t H&\geq \Delta H+2\langle\nabla v,\nabla H\rangle+\frac{H}{t}-2H\frac{\Delta \eta }{\eta}\\
&-\frac{2H}{t}(|\nabla \eta|^2 \frac{1}{\eta^2}+2\frac{t}{\eta} \langle \nabla v,\nabla \eta\rangle)\qquad \qquad (\text{took }2/t \text{ out})\\ 
&+\eta^2 t(\frac{2\alpha}{n} w^2)
\end{aligned}$$
One now sees after a long computation that the above inequality is equivalnet to the following 
\begin{equation}
\tag{\dagger}\label{HarVar}
\begin{aligned}
\partial_t H&\geq \Delta H+2\langle\nabla v,\nabla H\rangle\\
&-\frac{2H}{\eta^2}\left|\sqrt{\frac{2\alpha(1-\alpha)}{n}}\eta \nabla v+\frac{1}{\sqrt{\frac{2\alpha(1-\alpha)}{n}}}\nabla \eta\right|^2\\
&+\frac{H}{t\eta^2}[\eta^2-2\Delta \eta-2|\nabla \eta|^2+\frac{nt|\nabla \eta|^2}{2\alpha(1-\alpha)}+\frac{2\alpha}{n}H]\\
&-2|\nabla v|^2H\frac{2\alpha(1-\alpha)}{n}+2|\nabla v|^4t\eta^2\frac{(1-\alpha)^2\alpha}{n}
\end{aligned}
\end{equation}
Notice that we have the right signs for everything!

**Step 2. Carry out the maximum principle.** There exists some large \(C_{\alpha,n}\) such that 
$$\frac{n|\nabla \eta|^2}{2\alpha(1-\alpha)}\leq C_{\alpha,n}$$
Thus we have on \(B_{1/2}\times (0,T]\) where \(H\) is nonpositive,
$$\begin{aligned}
\partial_t H&\geq \Delta H+2\langle\nabla v,\nabla H\rangle\\
&+\frac{H}{t\eta^2}[1+C_{\alpha,n}t+\frac{2\alpha}{n}H]\\
\end{aligned}$$
Let 
$$h(x,t)=1+C_{\alpha,n}t+\frac{2\alpha}{n}H(x,t)\qquad (x,t)\in B_1\times [0,T]$$
We claim that \(h\geq 0\) on  \(B_{1/2}\times [0,T]\). Suppose not. Since \(h(x,t)\geq 0\) for \(x\in B_{1/2}\) and \(t\) close to \(0\), we see that there exists \((x_0,t_0)\in B_{1/2}\times (0,T]\) such that 
$$h(x_0,t_0)=\min_{(x,t)\in  B_{1/2}\times [0,T]}h(x,t)$$
and so, we have at \((x_0,t_0)\) that \(\partial_th\leq 0,\Delta h\geq 0,\nabla h=0\) which means at \((x_0,t_0)\), \(H\leq 0, \Delta H\geq 0\) and \(\nabla H=0\). But, at \((x_0,t_0)\), we have 
$$0\geq \frac{n}{2\alpha}(\partial_t h-C_{\alpha,n})=\partial_t H\geq 0$$
which is a contradiction! Thus, we have 
$$1+C_{\alpha,n}t+\frac{2\alpha}{n}H(x,t)\geq 0\qquad (x,t)\in B_{1/2}\times [0,T]$$
which gives 
$$\frac{n}{2\alpha t}+\frac{n}{2\alpha}C_{\alpha,n}+\frac{1}{t}H(x,t)\geq 0\qquad (x,t)\in B_{1/2}\times (0,T]$$
which finally arrives at 
$$\frac{n}{2\alpha t}+\frac{n}{2\alpha}C_{\alpha,n}+\Delta v+(1-\alpha)|\nabla v|^2\geq 0\qquad (x,t)\in B_{1/2}\times (0,T]$$
and that is the required Harnack! The proof of the theorem is complete. 

<span class="qed">∎</span>

</div>
Surprisingly, the proof yields the Harnack inequality on manifolds. 

<div class="theorem" id="theorem-4">

Let \(M^n\) be a complete \(n\)-dimensional Riemannian manifold, with non-negative Ricci curvature \(\operatorname{Ric}(M) \geq0\) and let \(B_{2 \rho}\) be a geodesic ball of radius \(2 \rho\) centered at some point \(p_0\) in \(M\). If \(u: M \times[0, \infty) \rightarrow[0, \infty)\) is a positive smooth solution to the heat equation 
$$\partial_t u=\Delta_g u\qquad M\times [0,\infty)$$
Let \(\alpha\in (0,1)\) and \(v=\log u\). Then the following holds on \(B_\rho \times(0, \infty)\), 
$$\partial_t v-\alpha |\nabla v|^2+\frac{n}{2\alpha t}\geq -\frac{C}{\rho^2}$$
where \(C=C(\alpha,n)\). In particular, sending \(\rho \to \infty\), and \(\alpha\to 1\), we obtain
$$\partial_t v- |\nabla v|^2+\frac{n}{2 t}\geq 0$$

</div>

<div class="proof">

<span class="proof-title">Proof.</span>

We have noted \((*)\) where we exchanged derivates in the previous proof. Set \(w:=\Delta v\), \(S=\Delta v+(1-\alpha)|\nabla v|^2\). Let \(\eta\in C_c^\infty(B_\rho (p_0))\) such that \(\eta\equiv 1\) on \(B_{\rho/2}(p_0)\) and \(\eta:M\to [0,1]\) such that on \(M\), 
$$|\nabla \eta|^2\leq C/\rho^2$$
Now we set 
$$H=t\eta^2 S$$
We get after a look at previous proof that 
$$\partial_t S=\Delta S+2\alpha |\nabla^2 v|^2+2\langle \nabla v,\nabla S\rangle+2\alpha \operatorname{Ric}(\nabla v,\nabla v)$$
and 
\begin{equation}
\tag{\dagger}\label{HarVar}
\begin{aligned}
\partial_t H&\geq \Delta H+2\langle\nabla v,\nabla H\rangle\\
&-\frac{2H}{\eta^2}\left|\sqrt{\frac{2\alpha(1-\alpha)}{n}}\eta \nabla v+\frac{1}{\sqrt{\frac{2\alpha(1-\alpha)}{n}}}\nabla \eta\right|^2\\
&+\frac{H}{t\eta^2}[\eta^2-2\Delta \eta-2|\nabla \eta|^2+\frac{nt|\nabla \eta|^2}{2\alpha(1-\alpha)}+\frac{2\alpha}{n}H]\\
&-2|\nabla v|^2H\frac{2\alpha(1-\alpha)}{n}+2|\nabla v|^4t\eta^2\frac{(1-\alpha)^2\alpha}{n}
\end{aligned}
\end{equation}
There exists some large \(C\) such that 
$$\frac{n|\nabla \eta|^2}{2\alpha(1-\alpha)}\leq \frac{C}{\rho^2}$$
Thus we have on \(B_{\rho/2}(p_0)\times (0,T]\) where \(H\) is nonpositive,
$$\begin{aligned}
\partial_t H&\geq \Delta H+2\langle\nabla v,\nabla H\rangle\\
&+\frac{H}{t\eta^2}[1+\frac{C}{\rho^2}t+\frac{2\alpha}{n}H]\\
\end{aligned}$$
The rest of the proof goes throughnd as before one gets at 
$$\frac{n}{2\alpha t}+\frac{C}{\rho^2}+\Delta v+(1-\alpha)|\nabla v|^2\geq 0\qquad (x,t)\in B_{1/2}\times (0,T]$$
proving the theorem. 

<span class="qed">∎</span>

</div>
If one is even more careful, one can derive the following theorem. 
<div class="theorem" id="theorem-5">

Let \(M^n\) be a complete \(n\)-dimensional Riemannian manifold, with non-negative Ricci curvature \(\operatorname{Ric}(M) \geq -\theta\) and let \(B_{2 \rho}\) be a geodesic ball of radius \(2 \rho\) centered at some point \(p_0\) in \(M\). If \(u: M \times[0, \infty) \rightarrow[0, \infty)\) is a positive smooth solution to the heat equation 
$$\partial_t u=\Delta_g u\qquad M\times [0,\infty)$$
Let \(\alpha\in (0,1)\) and \(v=\log u\). Then the following holds on \(B_\rho \times(0, \infty)\), 
$$\partial_t v-\alpha |\nabla v|^2+\frac{n}{2\alpha t}\geq -\frac{C}{\rho^2}-C\sqrt{\theta}\rho-C\theta$$
where \(C=C(\alpha,n)\). 
</div>
This theorem first appeared in Li-Yau's paper and was proved  in the more general situation for Schrödinger operators! 

Now let us look at some corollaries. 
<div class="theorem" id="theorem-6">

Suppose \(u \in C^{2,1}\left(\mathbb{R}^n \times(0, T]\right)\) satisfies
$$
u_t=\Delta u, \quad u>0 \quad \text { in } \mathbb{R}^n \times(0, T]
$$
Then \(v=\log u\) satisfies
$$
v_t-|\nabla v|^2+\frac{n}{2 t} \geq 0\quad \text { in } \mathbb{R}^n \times(0, T]
$$
</div>
<div class="proof">

<span class="proof-title">Proof.</span>

Let \(u_R(x,t):=u(Rx,R^2t)\) and \(v_R:=\log u_R\) and apply the Harnack on the unit ball to obtain 
$$\partial_t v_R-\alpha |\nabla v_R|^2+\frac{n}{2\alpha t}\geq -C\qquad B_{1/2}\times (0,T]$$
Unwinding, 
$$\partial_t v(Rx,R^2t)-\alpha |\nabla v|^2(Rx,R^2t)+\frac{n}{2\alpha t R^2}\geq -\frac{C}{R^2}\qquad B_{1/2}\times (0,T]$$
which means 
$$\partial_t v(x,t)-\alpha |\nabla v|^2(x,t)+\frac{n}{2\alpha t}\geq -\frac{C}{R^2}\qquad B_{R/2}\times (0,TR^2]$$
Take \(R\to \infty\) to obtain the theorem! 

<span class="qed">∎</span>

</div>

The differential Harnack inequality implies the Harnack inequality by integration! 
<div class="theorem" id="theorem-7">

Suppose \(u \in C^{2,1}\left(M\times(0, T]\right)\) satisfies
$$
\partial_t u=\Delta u, \quad u>0 \quad \text { on } M \times(0, T]
$$
Then for any \(\left(x_1, t_1\right),\left(x_2, t_2\right) \in M \times(0, T]\) with \(t_2>t_1>0\), we have 
$$\frac{u(x_2,t_2)}{u(x_1,t_1)}\geq \frac{t_1^{n/2}}{t_2^{n/2}}e^{-\frac{1}{4(t_2-t_1)}d_g(x_1,x_2)}$$

</div>

<div class="proof">

<span class="proof-title">Proof.</span>

Recall that \(v=\log u\) satisfies 
$$\partial_t v- |\nabla v|^2+\frac{n}{2 t}\geq 0$$
Let us consider a path \(\g:[t_1,t_2]\to M,\gamma(t_1)=x_1,\gamma(t_2)=x_2\). We integrate: 
$$\begin{aligned}
\log(\frac{u(x_1,t_1)}{u(x_2,t_2)})&=\int_{t_1}^{t_2}\partial_s [\log(u(\gamma(s),s))]\,ds\\
&=\int_{t_1}^{t_2}\frac{(\partial_t u)(\gamma(s),s)+\nabla u(\gamma(s),s)\cdot \gamma'(s)}{u(\gamma(s),s)}\\
&\geq \int_{t_1}^{t_2}|\nabla v|^2-\frac{n}{2s}+\nabla v\cdot \gamma'(s)\,ds\\
&=\int_{t_1}^{t_2}|\nabla v+\frac{1}{2}\gamma'(s)|^2-\frac{1}{4}|\gamma'(s)|^2-\frac{n}{2s}\,ds\\
&\geq -\frac{n}{2}\log(\frac{t_2}{t_1})-A
\end{aligned}$$
where we have written \(v(s)=v(\gamma(s),s)\). We have 
$$\frac{u(x_2,t_2)}{u(x_1,t_1)}\geq \frac{t_1^{n/2}}{t_2^{n/2}}e^{-A}$$
where 
$$A(x_1,x_2,t_1,t_2):=\inf \frac{1}{4}\int_{t_1}^{t_2}|\gamma'(s)|^2$$
where the infimum is taken over all paths \(\g:[t_1,t_2]\to M\), with \(\gamma(t_1)=x_1,\gamma(t_2)=x_2\). We need to bound \(A\) by above and that can be done by simply taking \(\sigma:[0,b]\to M\) to be the unit speed geodesic and taking $$\gamma(s):=\sigma(\varphi(t))\qquad \varphi(t)=\frac{b}{t_2-t_1}(t-t_1)$$
Then we get 
$$A\leq \frac{1}{4}\int_{0}^{t_2-t_1} \frac{b^2}{(t_2-t_1)^2}\,ds=\frac{1}{4(t_2-t_1)}d_g(x_1,x_2)$$
This yields us the result. 

<span class="qed">∎</span>

</div>
Specializing to Euclidean space, we obtain the following. 
<div class="theorem" id="theorem-8">


Suppose \(u \in C^{2,1}\left(\mathbb{R}^n \times(0, T]\right)\) satisfies
$$
u_t=\Delta u, \quad u>0 \quad \text { in } \mathbb{R}^n \times(0, T]
$$
Then for any \(\left(x_1, t_1\right),\left(x_2, t_2\right) \in \mathbb{R}^n \times(0, T]\) with \(t_2>t_1>0\),
$$
\frac{u\left(x_1, t_1\right)}{u\left(x_2, t_2\right)} \leq\left(\frac{t_2}{t_1}\right)^{\frac{n}{2}} \exp \left\{\frac{\left|x_2-x_1\right|^2}{4\left(t_2-t_1\right)}\right\}
$$
</div>
From here we obtain the classical version. 

<div class="theorem" id="theorem-9">
<strong>Classical Harnack on a manifold.</strong> 
Suppose \(u \in C^{2,1}\left(M\times(0, T]\right)\) satisfies
$$
\partial_t u=\Delta u, \quad u>0 \quad \text { on } M \times(0, T]
$$
Then for any compact subset \(K\), \(\left(x_1, t_1\right),\left(x_2, t_2\right) \in K \times(0, T]\) with \(t_2>t_1>0\), we have 
$$
u\left(x_1, t_1\right) \leq C u\left(x_2, t_2\right)
$$
where \(C\) is a positive constant depending only on \(n,K, t_2 / t_1\) and \(\left(t_2-t_1\right)^{-1}\). 
</div>
<div class="proof">

<span class="proof-title">Proof.</span>

We derived for any \(\left(x_1, t_1\right),\left(x_2, t_2\right) \in M \times(0, T]\) with \(t_2>t_1>0\), we have 
$$\frac{u(x_2,t_2)}{u(x_1,t_1)}\geq \frac{t_1^{n/2}}{t_2^{n/2}}e^{-\frac{1}{4(t_2-t_1)}d_g(x_1,x_2)}$$
One can easily bound the quantity on right by below and obtain the theorem.  

<span class="qed">∎</span>

</div>
We record the special case. 
<div class="theorem" id="theorem-10">
<strong>Classical Harnack.</strong> 
Suppose \(u \in C^{2,1}\left(B_1 \times(0,1]\right)\) satisfies
$$
u_t-\Delta u=0, u \geq 0 \quad \text { in } B_1 \times(0,1]
$$
Then for any \(\left(x_1, t_1\right),\left(x_2, t_2\right) \in B_{1 / 2} \times(0,1]\) with \(t_2>t_1\),
$$
u\left(x_1, t_1\right) \leq C u\left(x_2, t_2\right)
$$
where \(C\) is a positive constant depending only on \(n, t_2 / t_1\) and \(\left(t_2-t_1\right)^{-1}\).
</div>
The constant \(C\) is explicitly found out in a previous theorem. Notice unlike the Harnack inequality for harmonic function, here the time \(t_1,t_2\) cannot come very close to each other. A philosophical reason is that the Harnack is only due to \(\Delta\) and not \(\partial_t\). One can also see this on grounds of the heat kernel \(K_t(x)\) since \(K_t(0)\) blows up as \(t\to 0\). 

We end by mentioning Hamilton's generalization of the previous inequalities. 
<div class="theorem" id="theorem-11">
<strong>Li-Yau-Hamilton Harnack for the heat equation.</strong> 
Let \(M\) be a closed \(n\)-dimensional manifold, which is Ricci parallel, i.e. \(\nabla \operatorname{Ric}=0\), and has positive sectional curvature. If \(u: M \times[0, T] \rightarrow(0, \infty)\) is a non-negative solution to the heat equation
$$
\partial_t u=\Delta u, \quad x \in M, t \in[0, T] ,
$$
then the following inequality holds:
$$\nabla^2 u-\frac{\nabla u\otimes \nabla u}{u}+\frac{u}{2t}g\geq 0$$
</div>
This first appeared in Li-Yau's. paper and is more general than the Li-Yau Harnack inequality in the sense that if we trace this, we obtain the Li-yau Harnack inequality. For a similar inequality in the setting of Ricci flow, see the excellent book by B. Chow and P. Lu. 


## References

<ol>
  <li id="ref-B0">
    Chow, Bennett, and Dan Knopf. "The Ricci flow: an introduction." *Mathematical surveys and monographs* 110 (2011).
  </li>
  <li id="ref-Reto">
    Müller, Reto. *Differential Harnack inequalities and the Ricci flow*. Vol. 5. European Mathematical Society, 2006
  </li>
  <li id="ref-HRF">
    Chow, Bennett, Peng Lu, and Lei Ni. *Hamilton’s Ricci flow*. Vol. 77. American Mathematical Society, Science Press, 2023
  </li>
  <li id="ref-LiYau">
    Li, Peter, and Shing Tung Yau. "*On the parabolic kernel of the Schrödinger operator.*" (1986): 153-201.
  </li>
  <li id="ref-Ham">
    Hamilton, Richard S. "Matrix Harnack estimate for the heat equation." *Communications in analysis and geometry* 1.1 (1993): 113-126
  </li>
  <li id="ref-QHan">
    Han, Qing. *A basic course in partial differential equations*. Vol. 120. American Mathematical Soc., 2011.
  </li>
</ol>