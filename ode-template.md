---
title: "The ODE Template and Its Domain Equivalents"
subtitle: "Mechanical and electrical forms of one second-order equation"
author: "Hob Nilre & Bo C. Herlin"
date: "2026-10-08"
abstract: |
  Three linear relations and one balance produce the template
  $a\ddot y+b\dot y+cy=0$. Substituting coefficients and coordinates
  gives four forms: MCK, KCM, LRC and CRL. We derive their mappings,
  the reciprocal substitution between dual forms, and the scales
  that make the mechanical and electrical equations correspond exactly.
  The forced template also fixes the harmonic convention used by the companions.
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
time derivatives. For a common quantity $u$, define coordinates
$\dot y=u$, $h=au$, and three terms of the same dimension:
\begin{equation}
z_a=\dot h=a\dot u,\qquad z_b=bu,\qquad z_c=cy.
\label{eq:elements}
\end{equation}
Choose their signs so that the unforced balance is
$z_a+z_b+z_c=0$. Substitution gives
\begin{equation}
\boxed{a\ddot y+b\dot y+cy=0.}
\label{eq:template}
\end{equation}
The coefficients multiply the rate of $u$, $u$ itself, and its accumulated
coordinate. Their meanings determine the domain.

Write $T$ for the time dimension and $[z]$ for the common dimension of
the three terms. The defining relations require
\begin{equation}
[y]=[u]T,\qquad [h]=[z]T,\qquad
[a]=\frac{[z]T}{[u]},\quad [b]=\frac{[z]}{[u]},\quad
[c]=\frac{[z]}{[u]T}.
\label{eq:dimensions}
\end{equation}
The equivalent first-order system is
\begin{equation}
Dy=\frac ha,\qquad Dh=-cy-\frac ba h,
\label{eq:state}
\end{equation}
with initial coordinates $y(t_0)$ and $h(t_0)=a\dot y(t_0)$.

## Forcing and harmonic form

A prescribed sum gives $P_2(D)y=f$, $P_2(s)=as^2+bs+c$. Phasors use
$x(t)=\operatorname{Re}(\widehat x e^{\mathrm i\omega t})$,
$\mathrm i^2=-1$ and $\omega>0$. Thus $D$ multiplies a phasor by
$\mathrm i\omega$, and
\begin{equation}
\widehat f=P_2(\mathrm i\omega)\widehat y
=\left(a\mathrm i\omega+b+\frac{c}{\mathrm i\omega}\right)\widehat u,
\qquad \widehat u=\mathrm i\omega\widehat y.
\label{eq:phasor}
\end{equation}
The full solution retains its initial coordinates. Higher-order coefficients
and their phasor factors are derived in [*ODE Coefficient Synthesis*][synthesis].

# Four domain forms

In mechanics, let $m$ be mass, $d$ the damper coefficient and $k$
stiffness; use displacement $x$, velocity $v$, force $F$ and momentum
$p$.
In electrics, use inductance $L$, resistance $R$, capacitance $C$,
current $i$, voltage $e$, charge $q$ and flux linkage $\lambda$.
All parameters are positive constants.

| Template | MCK | KCM | LRC | CRL |
|:---------|:-----------:|:-----------:|:-----------:|:-----------:|
| $a$ | $m$ | $1/k$ | $L$ | $C$ |
| $b$ | $d$ | $1/d$ | $R$ | $1/R$ |
| $c$ | $k$ | $1/m$ | $1/C$ | $1/L$ |
| Common $u$ | $v$ | $F$ | $i$ | $e$ |
| Coordinate $h=au$ | $p$ | $x_s$ | $\lambda$ | $q$ |
| Coordinate $y$ | $x$ | $p$ | $q$ | $\lambda$ |
| Type of $z_j$ | Force | Velocity | Voltage | Current |

: The coefficient and quantity dictionary. Here $x_s$ is spring displacement; the last row identifies the quantity being summed. \label{tab:dictionary}

## MCK and LRC

For MCK, velocity is common and signed forces add. With $v=\dot x$
and $p=mv$, the terms are $\dot p=m\ddot x$, $d\dot x$ and $kx$.
For LRC, current is common and signed voltages add. With $i=\dot q$
and $\lambda=Li$, the terms are $\dot\lambda=L\ddot q$, $R\dot q$
and $q/C$. Their balances give
\begin{equation}
\boxed{m\ddot x+d\dot x+kx=0,\qquad
L\ddot q+R\dot q+\frac qC=0.}
\label{eq:mck-lrc}
\end{equation}
These are the mechanical parallel and electrical series forms.

## KCM and CRL

For KCM, force is common and signed velocities add. The relations
$\dot p=F$, $x_s=F/k$, $v_m=p/m$ give velocities $\dot F/k$, $F/d$
and $p/m$. For CRL, voltage is common and signed currents add. The
relations $\dot\lambda=e$, $q=Ce$, $i_L=\lambda/L$ give currents
$C\dot e$, $e/R$ and $\lambda/L$. Hence
\begin{equation}
\boxed{\frac{\ddot p}{k}+\frac{\dot p}{d}+\frac pm=0,\qquad
C\ddot\lambda+\frac{\dot\lambda}{R}+\frac\lambda L=0.}
\label{eq:kcm-crl}
\end{equation}
These are the mechanical series and electrical parallel forms.

# Correspondence and duality

## Changing domains

Choose positive conversion scales $\alpha,\beta$ and use the same time
variable. The force--voltage correspondence is
\begin{equation}
i\longleftrightarrow\alpha v,\qquad
e\longleftrightarrow\beta F,\qquad
L=\frac\beta\alpha m,\quad R=\frac\beta\alpha d,\quad
C=\frac\alpha{\beta k}.
\label{eq:scales}
\end{equation}
The scales convert units as well as numerical values. For MCK--LRC,
$(q,\lambda)=(\alpha x,\beta p)$; for KCM--CRL,
$(\lambda,q)=(\beta p,\alpha x_s)$. Direct substitution gives
\begin{align}
L\ddot q+R\dot q+\frac qC
&=\beta\bigl(m\ddot x+d\dot x+kx\bigr),
\label{eq:direct-map}\\
C\ddot\lambda+\frac{\dot\lambda}{R}+\frac\lambda L
&=\alpha\left(\frac{\ddot p}{k}+\frac{\dot p}{d}+\frac pm\right).
\label{eq:dual-domain-map}
\end{align}
Thus MCK corresponds to LRC, and KCM to CRL; initial coordinates
follow the same maps.

## Exchanging common and summed quantities

Construct the dual template by making a quantity $w$ common in place
of the $z_j$, and summing the corresponding quantities $u_j$.
Reversing the relations \eqref{eq:elements}, in reverse element order,
gives
$$
u_c=\frac{\dot w}{c},\qquad u_b=\frac wb,\qquad
u_a=\frac Ya,\qquad \dot Y=w.
$$
Here $Y=au_a$ is the coordinate associated with the original $a$
relation. The balance $u_c+u_b+u_a=0$ becomes
\begin{equation}
\boxed{\frac{\ddot Y}{c}+\frac{\dot Y}{b}+\frac Ya=0,\qquad
\mathcal D(a,b,c)=\left(\frac1c,\frac1b,\frac1a\right).}
\label{eq:duality}
\end{equation}
Applying $\mathcal D$ twice returns $(a,b,c)$. It sends MCK to KCM
and LRC to CRL, exactly as in Table \ref{tab:dictionary}.

Dividing each equation by its leading coefficient makes the effect
of this substitution explicit:
\begin{equation}
\ddot y+\frac ba\dot y+\frac ca y=0,
\qquad
\ddot Y+\frac cb\dot Y+\frac ca Y=0.
\label{eq:monic}
\end{equation}
The ratio $c/a$ is unchanged. The first-derivative coefficient changes
from $b/a$ to $c/b$; the two monic equations coincide exactly when
$b^2=ac$.

The scales change domains; the reciprocal map constructs the dual.
Coupled blocks and their initial coordinates are treated in
[*Interconnecting Series and Parallel ODEs*][interconnect]; signed power
and work are treated in [*Energy Ledgers for Forced Harmonic ODEs*][energy].

# References {-}

1. H. Nilre and B. C. Herlin (2026). [ODE Coefficient Synthesis][synthesis].
2. H. Nilre and B. C. Herlin (2026). [Interconnecting Series and Parallel ODEs][interconnect].
3. H. Nilre and B. C. Herlin (2026). [Energy Ledgers for Forced Harmonic ODEs][energy].

[synthesis]: https://github.com/hobnilre/physics-ode-coefficient-synthesis
[interconnect]: https://github.com/hobnilre/physics-ode-interconnect-ser-par
[energy]: https://github.com/hobnilre/physics-ode-energy
