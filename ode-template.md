---
title: "The ODE Template and Its Domain Equivalents"
subtitle: "Mechanical and electrical forms of one second-order equation"
author: "Hob Nilre & Bo C. Herlin"
date: "2026-10-08"
abstract: |
  Three linear relations and a balance give $a\ddot y+b\dot y+cy=f$.
  We derive its mechanical and electrical forms, the unit conversions
  between them, and the reciprocal map that exchanges common and summed
  quantities. Harmonic substitution gives the corresponding terminal ratio.
keywords:
  - ordinary differential equations
  - mechanical electrical analogy
  - second-order template
  - duality
---

\begingroup\scriptsize
\noindent PDF created: \pdfbuildtimestamp\par
\noindent Latest on GitHub: \url{https://github.com/hobnilre/physics-ode-template}\par
\endgroup

# The common template

Let $a,b,c>0$ be constants and $D=d/dt$; dots and primes also denote
time derivatives. For a common quantity $u$, define $\dot y=u$, $h=au$
and three terms of the same dimension:
\begin{equation}
z_a=\dot h=a\dot u,\qquad z_b=bu,\qquad z_c=cy.
\label{eq:elements}
\end{equation}
Their signed balance $z_a+z_b+z_c=0$ gives
\begin{equation}
\boxed{a\ddot y+b\dot y+cy=0.}
\label{eq:template}
\end{equation}
The terms depend on the rate of $u$, on $u$ itself, and on its accumulated
coordinate. Their physical meanings determine the domain.

With time dimension $T$, the defining relations require
\begin{equation}
[y]=[u]T,\qquad [h]=[z]T,\qquad
[a]=\frac{[z]T}{[u]},\quad [b]=\frac{[z]}{[u]},\quad
[c]=\frac{[z]}{[u]T}.
\label{eq:dimensions}
\end{equation}
Here $[z]$ is the common term dimension. The equivalent first-order form is
\begin{equation}
Dy=\frac ha,\qquad Dh=-cy-\frac ba h,
\label{eq:state}
\end{equation}
with initial coordinates $y(t_0)$ and $h(t_0)=a\dot y(t_0)$.

## Forcing and harmonic form

A prescribed sum gives $P_2(D)y=f$, where $P_2(s)=as^2+bs+c$.
For $x(t)=\operatorname{Re}(\widehat x e^{\mathrm i\omega t})$,
$\mathrm i^2=-1$ and $\omega>0$, differentiation multiplies the phasor
by $\mathrm i\omega$. Hence
\begin{equation}
\widehat f=P_2(\mathrm i\omega)\widehat y
=\left(a\mathrm i\omega+b+\frac{c}{\mathrm i\omega}\right)\widehat u,
\qquad \widehat u=\mathrm i\omega\widehat y.
\label{eq:phasor}
\end{equation}
This describes the harmonic component; the full solution also needs its
initial coordinates. [*ODE Coefficient Synthesis*][synthesis], Sections 1--3,
extends the dimension rule to coefficients of higher powers of $D$.

# Four domain forms

In mechanics use mass $m$, damping $d$, stiffness $k$, displacement $x$,
velocity $v$, force $F$ and momentum $p$. In electrics use inductance $L$,
resistance $R$, capacitance $C$, current $i$, voltage $e$, charge $q$ and
flux linkage $\lambda$. All parameters are positive constants.

| Template | MCK | KCM | LRC | CRL |
|:---------|:-----------:|:-----------:|:-----------:|:-----------:|
| $a$ | $m$ | $1/k$ | $L$ | $C$ |
| $b$ | $d$ | $1/d$ | $R$ | $1/R$ |
| $c$ | $k$ | $1/m$ | $1/C$ | $1/L$ |
| Common $u$ | $v$ | $F$ | $i$ | $e$ |
| Coordinate $h=au$ | $p$ | $x_s$ | $\lambda$ | $q$ |
| Coordinate $y$ | $x$ | $p$ | $q$ | $\lambda$ |
| Type of $z_j$ | Force | Velocity | Voltage | Current |

: Coefficients and coordinates; $x_s$ is spring displacement. The last row gives the quantity being summed. \label{tab:dictionary}

## MCK and LRC

For MCK, velocity is common and forces add: $v=\dot x$, $p=mv$,
and the three forces are $\dot p$, $dv$ and $kx$.
For LRC, current is common and voltages add: $i=\dot q$, $\lambda=Li$,
and the voltages are $\dot\lambda$, $Ri$ and $q/C$. Thus
\begin{equation}
\boxed{m\ddot x+d\dot x+kx=0,\qquad
L\ddot q+R\dot q+\frac qC=0.}
\label{eq:mck-lrc}
\end{equation}
These are mechanical parallel and electrical series forms. The forced
LRC equation is the starting point for the signed-power calculation in
[*Energy Ledgers for Forced Harmonic ODEs*][energy], Section 1.

## KCM and CRL

For KCM, force is common and velocities add. From $\dot p=F$ and
$x_s=F/k$, the velocities are $\dot F/k$, $F/d$ and $p/m$.
For CRL, voltage is common and currents add. From $\dot\lambda=e$
and $q=Ce$, the currents are $C\dot e$, $e/R$ and $\lambda/L$. Hence
\begin{equation}
\boxed{\frac{\ddot p}{k}+\frac{\dot p}{d}+\frac pm=0,\qquad
C\ddot\lambda+\frac{\dot\lambda}{R}+\frac\lambda L=0.}
\label{eq:kcm-crl}
\end{equation}
These are mechanical series and electrical parallel forms.
[*Interconnecting Series and Parallel ODEs*][interconnect], Sections 1--2,
uses the common and summed quantities to join whole blocks of either type.

# Correspondence and duality

## Changing domains

Choose positive conversion scales $\alpha,\beta$ and keep the time variable.
The force--voltage correspondence is
\begin{equation}
i\longleftrightarrow\alpha v,\qquad
e\longleftrightarrow\beta F,\qquad
L=\frac\beta\alpha m,\quad R=\frac\beta\alpha d,\quad
C=\frac\alpha{\beta k}.
\label{eq:scales}
\end{equation}
The scales convert units and values. With $(q,\lambda)=(\alpha x,\beta p)$
for MCK--LRC, and $(\lambda,q)=(\beta p,\alpha x_s)$ for KCM--CRL,
\begin{align}
L\ddot q+R\dot q+\frac qC
&=\beta\bigl(m\ddot x+d\dot x+kx\bigr),
\label{eq:direct-map}\\
C\ddot\lambda+\frac{\dot\lambda}{R}+\frac\lambda L
&=\alpha\left(\frac{\ddot p}{k}+\frac{\dot p}{d}+\frac pm\right).
\label{eq:dual-domain-map}
\end{align}
The equations and initial coordinates therefore transform together.

## Exchanging common and summed quantities

To construct the dual, make $w$ common in place of the $z_j$ and sum
the corresponding $u_j$. Reverse the relations in \eqref{eq:elements}
and their element order:
$$
u_c=\frac{\dot w}{c},\qquad u_b=\frac wb,\qquad
u_a=\frac Ya,\qquad \dot Y=w.
$$
Here $Y=au_a$. The balance $u_c+u_b+u_a=0$ gives
\begin{equation}
\boxed{\frac{\ddot Y}{c}+\frac{\dot Y}{b}+\frac Ya=0,\qquad
\mathcal D(a,b,c)=\left(\frac1c,\frac1b,\frac1a\right).}
\label{eq:duality}
\end{equation}
This reciprocal map sends MCK to KCM and LRC to CRL; applying it twice
returns $(a,b,c)$.

Dividing each equation by its leading coefficient gives
\begin{equation}
\ddot y+\frac ba\dot y+\frac ca y=0,
\qquad
\ddot Y+\frac cb\dot Y+\frac ca Y=0.
\label{eq:monic}
\end{equation}
The ratio $c/a$ is unchanged, while $b/a$ becomes $c/b$. The normalized
equations coincide exactly when $b^2=ac$. Changing domains rescales the
quantities; taking the dual exchanges what is common and what is summed.

# References {-}

1. H. Nilre and B. C. Herlin (2026). [ODE Coefficient Synthesis][synthesis].
2. H. Nilre and B. C. Herlin (2026). [Interconnecting Series and Parallel ODEs][interconnect].
3. H. Nilre and B. C. Herlin (2026). [Energy Ledgers for Forced Harmonic ODEs][energy].

[synthesis]: https://github.com/hobnilre/physics-ode-coefficient-synthesis
[interconnect]: https://github.com/hobnilre/physics-ode-interconnect-ser-par
[energy]: https://github.com/hobnilre/physics-ode-energy
