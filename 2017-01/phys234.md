# PHYS 234: Quantum Physics 1

These notes have been discontinued in favor of a formula sheet.

## Table of Contents

<!-- toc -->

Professor: Qing-Bin Lu

## History

You'd better know all this for Quiz 1 boi

### Equations

* Wien's empirical formula: $$ u(v)dv = c_1 v^3 e^{-c_2 v / T} dv $$
* Rayleigh-Jeans: $$ u(v)dv = \frac{8\pi}{c^3} k T v^2 dv $$
* Planck's good formula: $$ u(v)dv = c_1 v^3 (e^{-c_2 v / T} - 1) dv $$
* Planck-Einstein relation: $$ E = hv $$, $$ p = E / c = h / \lambda $$
* Light intensity: $$ I = nhv $$
* Work function of metal / ionization energy of gas: $$ hv \geq \Phi $$
* Maximum kinetic energy of emitted electrons: $$ hv - \Phi $$

### By topic

* Blackbody radiation: Wien's empirical formula only worked for high frequency, Rayleigh-Jeans only worked for low frequency (ultraviolet catastrophe). Planck's worked for all frequencies and was explained by energy quanta.
* Photoelectric effect: Hertz noticed sparks from metals. Lenard noticed that gases did this too. Einstein explained this using light quanta.
* Solid heat capacity: Einstein explained using energy quanta.
* Atomic spectra: Hydrogen emits in several series. Lyman, Balmer, Paschen are first three. Balmer's formula is miraculous.
* Atomic model: Thomson came up with plum pudding. Rutherford disproves with gold foil / \alpha scattering experiment, comes up with planetary model. Bohr extends this model to be very good.

### By person 
* Heinrich Hertz: Initially observed photoelectric effect.
* Wien: Did an empirical formula for blackbody radiation.
* JJ Thompson: Discovered the electron. Plum pudding model.
* Philipp Lenard: Gases also emit electrons
* Rayleigh-Jeans: Did a bad EM-theory based formula for blackbody radiation.
* Kelvin: Two dark clouds
* Einstein: Photoelectric effect, solid heat capacity, and more!
* Millikan: Oil drop experiment, cosmic rays
* Bohr: Model of atom, orbitals.
* Balmer: Four hydrogen lines formula
* Rutherford: Gold foil experiment
* Pauli: Exclusion principle
* Heisenberg: Matrix mechanics
* Schrödinger: Wave mechanics

### By date

* 1887: Heinrich Hertz recognized sparks.
* 1894: Wien's empirical formula (high frequency)
* 1897: JJ Thompson discovers the electron.
* 1900: Lenard finds gases also emit electrons
* 1900: Rayleigh-Jeans equation (low frequency)
* 1900: Max Planck's empirical formula, explained using energy quanta
* 1900: Kelvin's two "dark clouds" (no ether, ultraviolet catastrophe)
* 1904: JJ Thompson's plum pudding model
* 1905: Einstein explained photoelectric effect using light quanta
* 1905: Einstein's annus mirabilis
* 1907: Einstein explained solid heat capacity, using energy quanta
* 1909: Millikan's water drop experiment
* 1910: Millikan's oil drop experiment
* 1913: Bohr's model of atom. Culmination of Old Quantum Theory.
* 1914: Millikan verifies linear relationship between radiation frequency and electron energy
* 1921: Millikan proves cosmic rays come from space
* 1923: Compton further verifies Einstein on EM
* 1925: Pauli's exclusion principle
* 1925: Heisenberg's matrix mechanics
* 1926: Schrödinger's wave mechanics

### Nobel Prizes

* 1906: J.J Thompson, for gas conductance
* 1921: Einstein, for photoelectric effect
* 1922: Bohr, for atom structure
* 1923: Millikan, for elementary charge
* 1932: Heisenberg
* 1933: Schrödinger and Dirac

### Facts

* Einstein's five miracle papers
  * Photoelectric effect, atoms exist, Brownian motion, special relativity, E = mc^2
* Correspondence principle
  * Quantum theory needs to agree with classical theory only with very large quantum numbers
* Bohr-Kramers-Slater theory (BKS)
  * Failed attempt to extend Bohr model
* Pauli Exclusion Principle
  * Each quantum state can only hold one electron
* Three applications of QT
  * Transistors, lasers, scanning tunneling microscope
* Quantum numbers
  * n. k from 1 to n. m from -k to k exclusive. s \pm 1/2.

### Michelson-Morley experiment

Failed to measure any movement relative to the "luminiferous aether".

### Photoelectric effect

Einstein proposed **light quanta** to explain the photoelectric effect. He later used energy quanta to explain the heat capacity of solids.

## De Broglie's matter wave

De Broglie rearranged Einstein's equation to get

$$
p = \frac{h}{\lambda}
$$

and extended it from photons to electrons, ions, and all other particles. Einstein said that this was "the first feeble ray of light on the worst of our physics enigmas".

Know this for Quiz 2 or it will trigger you forever.

## Wave functions

$$\Psi(x,t)$$ is a wave function. It describes a quantum state. It must be square-integrable and continuous in space.

### The Schrödinger Equation

$$
i \hbar \frac{\partial \Psi}{\partial t} = \left[ -\frac{\hbar^2}{2m} \nabla^2 + V \right] \Psi
$$

This is the $$F=ma$$ of quantum mechanics. It tells you how the wave function evolves over time. It came out Schrödinger's mind — it cannot be derived from existing equations. But see [here](http://hyperphysics.phy-astr.gsu.edu/hbase/quantum/Schr2.html#c1) for an intuition of how he may have come up with it.

### Statistical interpretation of the wave function

The probability of finding a particle described by $$\Psi(x,t)$$ in the region $$x$$ to $$x+dx$$ is

$$
P(x,t)dx = | \Psi(x,t) |^2 dx = \Psi^{*} \Psi
$$

We call $$P(x,t)$$ the probability amplitude or probability density. For this to make sense, $$\Psi$$ must be normalized, i.e.

$$
\int_{-\infty}^\infty P(x,t)dx = 1
$$

Once $$\Psi$$ is normalized, it will stay normalized as it evolves over time according to the Schrödinger equation. To see this, show that $$ \frac{d}{dt} \int |\Psi|^2 dx = 0 $$.

### Momentum

The momentum-space wave function $$\Phi(p,t)$$ is another wave function. It is the Fourier transform of the position-space wave function.

$$
\begin{eqnarray}
\Psi(x,t) = \frac{1}{\sqrt{2\pi\hbar}} \int e^{ipx/\hbar} \Phi(p,t)dx \\
\Phi(p,t) = \frac{1}{\sqrt{2\pi\hbar}} \int e^{-ipx/\hbar} \Psi(x,t)dx
\end{eqnarray}
$$

The momentum probability density is $$\rho(p,t) = |\Phi(p,t)|^2 = \Phi^* \Phi$$, basically just like $$P$$ and $$\Psi$$. It follows the same normalization conditions too.

The expectation value of momentum can also be calculated as

$$
\left\langle p \right\rangle = \frac{d\left\langle x \right\rangle}{dt}
$$

To see this, expand, move the derivative into the integral, use the Schrödinger equation to obtain and apply $$ \frac{\partial}{\partial t} |\Psi|^2 = \frac{\partial}{\partial x} \left[ \frac{i\hbar}{2m} \left(\Psi^* \frac{\partial\Psi}{\partial x} - \frac{\partial\Psi^*}{\partial x} \Psi \right) \right] $$, and integrate by parts twice.

### Operators

If you calculate the expectation value of momentum, you get

$$
\bar{p} = \left\langle p \right\rangle = \int \Psi^* \hat{p} \Psi dx
$$

where $$\hat{p} = -i\hbar \frac{\partial}{\partial x} = -i\hbar\nabla$$ is the **momentum operator**.

Now that we have the momentum operator, we can derive other operators based on it. These let us compute the expectation value of other quantities — in fact, any dynamical quantity. For example:

- Kinetic energy: $$T = \frac{1}{2} mv^2 = \frac{p^2}{2m}$$, so $$\hat{T} = \frac{-\hbar^2\nabla^2}{2m}$$
- Angular momentum: $$\vec{L} = \vec{r} \times \vec{p}$$, so $$\hat{\vec{L}} = -i\hbar(\vec{r} \times \nabla)$$

In general, the expectation value of any dynamical quantity $$Q(x,p)$$ is $$\bar{Q}(x,p) = \left\langle Q(x,p) \right\rangle = \int \Psi^* Q(x, -i\hbar\nabla) \Psi dx$$.

### The uncertainty principle

The more precisely you know position, the less precisely you can possibly know momentum, and vice-versa.

$$
\sigma_x \sigma_p \geq \hbar / 2
$$

where $$\sigma_x = \left(\left\langle x^2 \right\rangle - \left\langle x \right\rangle ^2\right)^\frac{1}{2}$$, similar for $$\sigma_p$$.

Proof is TODO. For intuition, think about the jump rope. You can also think about $$ p = h / \lambda $$.

## Solving the Schrödinger equation

### Separable solutions and the TISE

Suppose that $$ \Psi(x,t) = \psi(x) \phi(t) $$. By plugging this into the Schrödinger equation, dividing through by $$\psi\phi$$, and noticing both sides must be constant, we can obtain

$$
\phi(t) = e^{-iEt/\hbar}
$$

where the constant $$ E $$ is the energy of the state. The Hamiltonian is

$$
H(x,p) = \frac{p^2}{2m} + V(x)
$$

(i.e. total energy = kinetic + potential). That means the Hamiltonian operator is

$$
\hat{H} = -\frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2} + V
$$

This lets write the time independent Schrödinger equation (TISE) as:

$$
\begin{eqnarray}
-\frac{\hbar^2}{2m} \frac{d^2 \psi}{dx^2} + V\psi & = & E \psi \\
\hat{H} \psi & = & E \psi
\end{eqnarray}
$$

This equation has solutions in the form $$ \Psi(x,t) = \psi(x) e^{iEt/\hbar} $$. These solutions are all stationary states ($$|\Psi|^2$$ doesn't change over time) and have definite total energy $$ E $$.

**Every solution of the general Schrödinger equation can be written as a linear combination of these separable solutions.**

### The infinite square potential well

This is when we have $$V(x) = 0$$ if $$ x \leq 0 \leq a $$, $$ \infty $$ otherwise.

The separable solution can be obtained by solving the TISE and normalizing. It is

$$
\psi_n(x) = \sqrt{\frac{2}{a}} \sin \left(\frac{n\pi x}{a}\right)
$$

Energy is $$ E_n = \frac{n^2 \pi^2 \hbar^2}{2ma^2} $$.

- Cool facts:
  1. $$ E_1 = \frac{\pi^2 \hbar^2}{2ma^2} $$ — the minimal energy is more than zero. (Can understand through uncertainty principle)
  2. $$ E_n \sim n^2 $$. Can show this by considering $$ \Delta E $$ for some $$n$$. As $$ n \to \infty $$, $$ \frac{\Delta E_n}{E_n} \to 0 $$ and the energy is eventually like a continuum. This is Bohr's correspondence principle.
  3. $$ \psi_n(x) $$ are **mutually orthogonal**, i.e. $$ \int \psi^*_m(x) \psi_n(x) = \delta_{mn} $$ (the Kronecker delta). Can see by using trig rules.
  4. $$ \psi_n(x) $$ is **complete**. Any other function $$f(x)$$ from 0 to a is a linear combination of the functions in that family.

The Fourier Trick lets you obtain the coefficients for the linear combination:

$$
c_n = \int \psi_n(x)^* f(x) dx
$$

In particular, this means that the general solution for the infinite square potential well is

$$
\Psi(x,t) = \sum_{n=1}^\infty c_n \sqrt{\frac{2}{a}} \sin \left( \frac{n\pi x}{a} \right) e^{-i(n^2 \pi^2 \hbar / 2ma^2)t}
$$

where

$$
c_n = \sqrt{\frac{2}{a}} \int_0^a \sin \left( \frac{n\pi x}{a} \right) \Psi(x, 0) dx
$$

### The harmonic oscillator

We can locally approximate any potential well with a parabola. Then, $$ V(x) = \frac{1}{2} m \omega^2 x^2 $$, and

$$
\begin{eqnarray}
H &=& \frac{p^2}{2m} + \frac{1}{2} m \omega^2 x^2 \\
  &=& \frac{\hat{p}^2}{2m} + \frac{1}{2} m \omega^2x^2
\end{eqnarray}
$$

where $$\hat{p} = -i\hbar \frac{\partial}{\partial x}$$, $$\omega$$

#### Algebraic method

To solve the Schrödinger equation for this case, rewrite it like this.

$$
\begin{eqnarray}
-\frac{\hbar^2}{2m} \frac{d^2\psi}{dx^2} + \frac{1}{2}m \omega^2 x^2 \psi &=& E \psi \\
\frac{1}{2m} [p^2 + (m\omega x)^2] \psi &=& E\psi \\
\end{eqnarray}
$$

We introduce the ladder operators

$$
a_\pm = \frac{1}{\sqrt{2\hbar m \omega}} (\mp i \hat{p} + m\omega x)
$$

And the commutator

$$
\begin{eqnarray}
[x,\hat{p}] &=& x\hat{p} - \hat{p}x
            &=& i \hbar
\end{eqnarray}
$$

One can check that this means $$ a_\mp a_\pm = \frac{1}{\hbar \omega} \hat{H} \pm \frac{1}{2} $$. So we can write $$ \hat{H} = \hbar \omega (a_\mp a_\pm \mp \frac{1}{2}) $$.

$$ a_+ $$ is called the raising operator and $$ a_- $$ is called the lowering operator, since

$$
\hat{H} (a_\pm \Psi) = (E \pm \hbar \omega)(a_\pm \Psi)
$$

This means that the lowest energy state of the harmonic oscillator is given by

$$
\begin{eqnarray}
a_- \psi_0 & = & 0 \\
\psi_0 & = & \left( \frac{m\omega}{\pi\hbar} \right)^{(1/4)} e^{-m\omega x^2/2\hbar}
\end{eqnarray}
$$

with an energy of $$ \frac{1}{2} \hbar \omega $$. So allowable energy levels are $$ \left( \frac{1}{2} + k \right) \hbar \omega $$ for natural numbers $$k$$.

So the separable solutions to the harmonic oscillator are

$$
\psi_n(x) = \frac{1}{\sqrt(n!)} (a_+)^n \psi_0(x)
$$

(You can prove the $$\frac{1}{\sqrt(n!)}$$ normalization part with some Hermitian operator stuff.)

In particular, you should know this:

$$
\begin{eqnarray}
a_+ \psi_n & = & \sqrt{n+1} \psi_n+1 \\
a_- \psi_n & = & \sqrt{n} \psi_{n-1}
\end{eqnarray}
$$

#### Analytic method

TODO
