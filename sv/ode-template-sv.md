---
title: "ODE-mallen och dess motsvarigheter i olika domäner"
subtitle: "Mekaniska och elektriska former av en ekvation av andra ordningen"
author: "Hob Nilre & Bo C. Herlin"
date: "2026-10-08"
lang: sv
abstract: |
  Tre linjära samband och en balans ger $a\ddot y+b\dot y+cy=f$.
  Vi härleder dess mekaniska och elektriska former, enhetsomvandlingarna
  mellan dem och den reciproka avbildning som byter plats på gemensamma
  och summerade storheter. En harmonisk ansats ger motsvarande kvot
  mellan terminalstorheterna.
keywords:
  - ordinära differentialekvationer
  - mekanisk elektrisk analogi
  - mall av andra ordningen
  - dualitet
---

\begingroup\scriptsize
\noindent PDF created: \pdfbuildtimestamp\par
\noindent Latest on GitHub: \url{https://github.com/hobnilre/physics-ode-template}\par
\noindent Svensk översättning av \href{https://github.com/hobnilre/physics-ode-template/blob/main/ode-template.md}{den engelska originalartikeln}.\par
\endgroup

# Den gemensamma mallen

Låt $a,b,c>0$ vara konstanter och $D=d/dt$; punkter och primtecken
betecknar också tidsderivator. För en gemensam storhet $u$, definiera
$\dot y=u$, $h=au$ och tre termer med samma dimension:
\begin{equation}
z_a=\dot h=a\dot u,\qquad z_b=bu,\qquad z_c=cy.
\label{eq:elements}
\end{equation}
Deras balans med tecken, $z_a+z_b+z_c=0$, ger
\begin{equation}
\boxed{a\ddot y+b\dot y+cy=0.}
\label{eq:template}
\end{equation}
Termerna beror på ändringstakten hos $u$, på $u$ självt och på dess
ackumulerade koordinat. Deras fysikaliska betydelser bestämmer domänen.

Med tidsdimensionen $T$ kräver de definierande sambanden
\begin{equation}
[y]=[u]T,\qquad [h]=[z]T,\qquad
[a]=\frac{[z]T}{[u]},\quad [b]=\frac{[z]}{[u]},\quad
[c]=\frac{[z]}{[u]T}.
\label{eq:dimensions}
\end{equation}
Här är $[z]$ termernas gemensamma dimension. Den ekvivalenta formen
av första ordningen är
\begin{equation}
Dy=\frac ha,\qquad Dh=-cy-\frac ba h,
\label{eq:state}
\end{equation}
med begynnelsekoordinaterna $y(t_0)$ och $h(t_0)=a\dot y(t_0)$.

## Drivning och harmonisk form

En föreskriven summa ger $P_2(D)y=f$, där $P_2(s)=as^2+bs+c$.
För $x(t)=\operatorname{Re}(\widehat x e^{\mathrm i\omega t})$,
$\mathrm i^2=-1$ och $\omega>0$ motsvarar derivering multiplikation
av fasorn med $\mathrm i\omega$. Alltså
\begin{equation}
\widehat f=P_2(\mathrm i\omega)\widehat y
=\left(a\mathrm i\omega+b+\frac{c}{\mathrm i\omega}\right)\widehat u,
\qquad \widehat u=\mathrm i\omega\widehat y.
\label{eq:phasor}
\end{equation}
Detta beskriver den harmoniska komponenten; den fullständiga lösningen
kräver även begynnelsekoordinaterna. [*ODE Coefficient Synthesis*][synthesis],
avsnitt 1--3, utvidgar dimensionsregeln till koefficienter för högre
potenser av $D$.

# Fyra domänformer

I mekaniken används massa $m$, dämpning $d$, styvhet $k$, förskjutning $x$,
hastighet $v$, kraft $F$ och rörelsemängd $p$. I elläran används induktans $L$,
resistans $R$, kapacitans $C$, ström $i$, spänning $e$, laddning $q$ och
flödeslänkning $\lambda$. Alla parametrar är positiva konstanter.

| Mall | MCK | KCM | LRC | CRL |
|:--------------------|:-----------:|:-----------:|:-----------:|:-----------:|
| $a$ | $m$ | $1/k$ | $L$ | $C$ |
| $b$ | $d$ | $1/d$ | $R$ | $1/R$ |
| $c$ | $k$ | $1/m$ | $1/C$ | $1/L$ |
| Gemensam $u$ | $v$ | $F$ | $i$ | $e$ |
| Koordinat $h=au$ | $p$ | $x_s$ | $\lambda$ | $q$ |
| Koordinat $y$ | $x$ | $p$ | $q$ | $\lambda$ |
| Typ av $z_j$ | Kraft | Hastighet | Spänning | Ström |

: Koefficienter och koordinater; $x_s$ är fjäderns förskjutning. Den sista raden anger vilken storhet som summeras. \label{tab:dictionary}

## MCK och LRC

För MCK är hastigheten gemensam och krafterna adderas: $v=\dot x$,
$p=mv$, och de tre krafterna är $\dot p$, $dv$ och $kx$.
För LRC är strömmen gemensam och spänningarna adderas: $i=\dot q$,
$\lambda=Li$, och spänningarna är $\dot\lambda$, $Ri$ och $q/C$. Alltså
\begin{equation}
\boxed{m\ddot x+d\dot x+kx=0,\qquad
L\ddot q+R\dot q+\frac qC=0.}
\label{eq:mck-lrc}
\end{equation}
Detta är mekanisk parallellkoppling respektive elektrisk seriekoppling.
LRC-ekvationen med drivning är utgångspunkten för effektberäkningen
med tecken i [*Energy Ledgers for Forced Harmonic ODEs*][energy],
avsnitt 1.

## KCM och CRL

För KCM är kraften gemensam och hastigheterna adderas. Från $\dot p=F$
och $x_s=F/k$ fås hastigheterna $\dot F/k$, $F/d$ och $p/m$.
För CRL är spänningen gemensam och strömmarna adderas. Från
$\dot\lambda=e$ och $q=Ce$ fås strömmarna $C\dot e$, $e/R$ och
$\lambda/L$. Därmed
\begin{equation}
\boxed{\frac{\ddot p}{k}+\frac{\dot p}{d}+\frac pm=0,\qquad
C\ddot\lambda+\frac{\dot\lambda}{R}+\frac\lambda L=0.}
\label{eq:kcm-crl}
\end{equation}
Detta är mekanisk seriekoppling respektive elektrisk parallellkoppling.
[*Interconnecting Series and Parallel ODEs*][interconnect], avsnitt 1--2,
använder de gemensamma och summerade storheterna för att koppla samman
hela block av båda typerna.

# Motsvarighet och dualitet

## Byte av domän

Välj positiva omvandlingsskalor $\alpha,\beta$ och behåll tidsvariabeln.
Motsvarigheten mellan kraft och spänning är
\begin{equation}
i\longleftrightarrow\alpha v,\qquad
e\longleftrightarrow\beta F,\qquad
L=\frac\beta\alpha m,\quad R=\frac\beta\alpha d,\quad
C=\frac\alpha{\beta k}.
\label{eq:scales}
\end{equation}
Skalorna omvandlar enheter och värden. Med $(q,\lambda)=(\alpha x,\beta p)$
för MCK--LRC och $(\lambda,q)=(\beta p,\alpha x_s)$ för KCM--CRL gäller
\begin{align}
L\ddot q+R\dot q+\frac qC
&=\beta\bigl(m\ddot x+d\dot x+kx\bigr),
\label{eq:direct-map}\\
C\ddot\lambda+\frac{\dot\lambda}{R}+\frac\lambda L
&=\alpha\left(\frac{\ddot p}{k}+\frac{\dot p}{d}+\frac pm\right).
\label{eq:dual-domain-map}
\end{align}
Ekvationerna och begynnelsekoordinaterna omvandlas alltså tillsammans.

## Byte mellan gemensamma och summerade storheter

För att bilda dualen, gör $w$ gemensam i stället för $z_j$ och summera
motsvarande $u_j$. Vänd på sambanden i \eqref{eq:elements} och på
elementens ordning:
$$
u_c=\frac{\dot w}{c},\qquad u_b=\frac wb,\qquad
u_a=\frac Ya,\qquad \dot Y=w.
$$
Här är $Y=au_a$. Balansen $u_c+u_b+u_a=0$ ger
\begin{equation}
\boxed{\frac{\ddot Y}{c}+\frac{\dot Y}{b}+\frac Ya=0,\qquad
\mathcal D(a,b,c)=\left(\frac1c,\frac1b,\frac1a\right).}
\label{eq:duality}
\end{equation}
Denna reciproka avbildning för MCK till KCM och LRC till CRL;
två tillämpningar återger $(a,b,c)$.

Division av varje ekvation med dess ledande koefficient ger
\begin{equation}
\ddot y+\frac ba\dot y+\frac ca y=0,
\qquad
\ddot Y+\frac cb\dot Y+\frac ca Y=0.
\label{eq:monic}
\end{equation}
Kvoten $c/a$ är oförändrad, medan $b/a$ blir $c/b$. De normaliserade
ekvationerna sammanfaller precis när $b^2=ac$. Ett domänbyte skalar
om storheterna; dualbildning byter vad som är gemensamt och vad
som summeras.

# Referenser {-}

1. H. Nilre och B. C. Herlin (2026). [ODE Coefficient Synthesis][synthesis].
2. H. Nilre och B. C. Herlin (2026). [Interconnecting Series and Parallel ODEs][interconnect].
3. H. Nilre och B. C. Herlin (2026). [Energy Ledgers for Forced Harmonic ODEs][energy].

[synthesis]: https://github.com/hobnilre/physics-ode-coefficient-synthesis
[interconnect]: https://github.com/hobnilre/physics-ode-interconnect-ser-par
[energy]: https://github.com/hobnilre/physics-ode-energy
