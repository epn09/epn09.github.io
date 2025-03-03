---
layout: home
title: "Force-Restore Model"
date: 2025-02-28
---

# Force-Restore Model

Assume that temperature is horizontally uniform.
Let $$ T(t, z) $$ be a temperature function.

<p>
The heat equation is
\begin{equation}
\rho c_p \frac{\partial T}{\partial t} = \lambda \frac{\partial^2 T}{\partial z^2},
\label{eq:pde}
\end{equation}
where \( \rho c_p~(\mathrm{W\,s/m^3\,K}) \) is volumetric heat capacity
and \( \lambda~(\mathrm{W/m\,K}) \) is thermal conductivity.
</p>

<p>
The form of the PDE suggests that its general solution is
\begin{equation}
T(t, z) = \overline{T} + \Delta T \exp (i \omega t) \exp (a_z z),
\label{eq:pde_gen_sol}
\end{equation}
where, \( a_z \) must have a negative real part so that temperature fluctuates
less as we go deeper.
As \( z \to \infty \), we have \( T \to \overline{T} \).
Therefore, \( \overline{T} \) is also considered to be the temperature of a very deep
soil layer that is unaffected by external forcing.
</p>

<p>
Define \( T_s \) to be surface temperature, for convenience.
Thus,
\begin{equation}
T_s(t) = T(t, 0) = \overline{T} + \Delta T \exp(i \omega t).
\label{eq:t_s}

\end{equation}
Substitute \eqref{eq:pde_gen_sol} into the PDE \eqref{eq:pde} and simplify, we have
$$ \rho c_p i \omega = \lambda a_z^2, $$
implying
$$ a_z = -\sqrt{i\omega \rho c_p / \lambda} = -(1 + i) \sqrt{\omega \rho c_p / 2\lambda}. $$
The negative sign is to ensure that soil temperature fluctuates less as we go
deeper.
</p>

<p>
At the surface, let \( G(t) \) be the heat flux into the ground, we have,
$$ G(t) = -\lambda \left. \frac{\partial T}{\partial z} \right|_{z = 0}. $$
When \( G(t) > 0 \), temperature is higher in the shallower layer, i.e., \( \partial T/\partial z < 0 \).
Therefore, we have the minus sign before \( \lambda \).
Substituting \eqref{eq:pde_gen_sol} and \( z = 0 \), we have
\begin{equation}
\begin{split}
G(t) & = -\lambda a_z \Delta T \exp(i\omega t) \\
&  = -\lambda a_z (T_s - \overline{T}) \\
& = \lambda (1 + i) (T_s - \overline{T}) \sqrt{\omega \rho c_p / 2 \lambda} \\
& = \omega (1 + i) (T_s - \overline{T}) \sqrt{\rho c_p \lambda / 2 \omega} \\
& = (\omega (T_s - \overline{T}) + i \omega(T_s - \overline{T}))  \frac{\mu}{\sqrt{2 \omega}},
 \end{split}
 \label{eq:g_1}
\end{equation}
where \( \mu = \sqrt{\rho c_p \lambda} \, (\mathrm{W\,\sqrt{s}/m^2\,K}) \) is
also called thermal effusivity or thermal inertia.
Differentiating \eqref{eq:t_s} by \( t \), we have,
$$
\frac{\partial T_s}{\partial t} = i \omega \Delta T \exp(i \omega t)
= i \omega (T_s - \overline{T}),
$$
Substituting into \eqref{eq:g_1} and simplify, we get,
$$
G(t)
= \left[
    \omega (T_s - \overline{T}) + \frac{\partial T_s}{\partial t}
    \right] \frac{\mu}{\sqrt{2 \omega}},
$$
which is a relation linking ground heat flux with surface temperature and its
time-derivative.
</p>

## Phase lead of ground heat flux

<p>
We can also write \( G(t) \) as
\begin{equation*}
\begin{split}
G(t) & = -\lambda a_z \Delta T \exp(i\omega t) \\
& = \lambda \sqrt{i \omega \rho c_p / \lambda} \Delta T \exp(i \omega t) \\
& = \sqrt{\omega \rho c_p \lambda} \Delta T \exp(i \omega t) \sqrt{i} \\
& = \sqrt{\omega \rho c_p \lambda} \Delta T \exp(i \omega t) \exp(i \pi / 4) \\
& = \sqrt{\omega \rho c_p \lambda} \Delta T \exp(i (\omega t + \pi / 4)).
\end{split}
\end{equation*}

Thus, \( G \) leads \( T_s \) by \( \pi / 4 \), that is, 1/8 of a
cycle.
When a cycle is a year (i.e., 12 months), 1/8 is 1.5 months.
It helps explain why \( G \) peaks around June but the hottest month (i.e., \(
T_s \) peak) is around July and August, in the Northern Hemisphere.
Similarly, it also helps explain why December is not the coldest month and
why the hottest hours of the day is usually in the afternoon.
</p>

## References
* Dickinson, R. E. (1988).
The force-restore model for surface temperatures and its generalizations.
*Journal of Climate, 1*(11), 1086-1097. [https://doi.org/10.1175/1520-0442(1988)001<1086:TFMFST>2.0.CO;2](https://doi.org/10.1175/1520-0442(1988)001<1086:TFMFST>2.0.CO;2)
* Hirota, T., Pomeroy, J. W., Granger, R. J., & Maule, C. P. (2002).
An extension of the force-restore method to estimating soil temperature at depth and evaluation for frozen soils under snow.
*Journal of Geophysical Research: Atmospheres, 107*(D24), 4767. <https://doi.org/10.1029/2001JD001280>
