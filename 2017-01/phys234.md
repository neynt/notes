# PHYS 234: Quantum Physics 1

Professor: Qing-Bin Lu
## History

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

## Wave functions

$$\Psi(x,t)$$ is the wave function. It describes a quantum state.

### The Schrödinger Equation

$$
i \hbar \frac{\partial \Psi(x,t)}{\partial t} = \left[ -\frac{\hbar^2}{2m} \nabla^2 + V \right] \Psi(x,t)
$$

This is the $$F=ma$$ of quantum mechanics. It tells you how the wave function evolves over time. How did Schrödinger obtain this equation? See [here](http://hyperphysics.phy-astr.gsu.edu/hbase/quantum/Schr2.html#c1) for an intuition.

### Properties of $$\Psi$$

$$\Psi$$ must be square-integrable and continuous in space.

### Statistical interpretation

The probability of finding a particle described by $$\Psi(x,t)$$ in the region $$x$$ to $$x+dx$$ is

$$
P(x,t)dx = | \Psi(x,t) |^2 dx = \Psi^{*} \Psi
$$

We call $$P(x,t)$$ the probability amplitude or probability density. For this to make sense, $$\Psi$$ must be normalized, i.e.

$$
\int_{-\infty}^\infty P(x,t)dx = 1
$$

### Momentum

The momentum-space wave function $$\Phi(p,t)$$ is another wave function. It is the Fourier transform of the position-space wave function.

$$
\begin{eqnarray}
\Psi(x,t) = \frac{1}{\sqrt{2\pi\hbar}} \int e^{ipx/\hbar} \Phi(p,t)dx \\
\Phi(p,t) = \frac{1}{\sqrt{2\pi\hbar}} \int e^{-ipx/\hbar} \Psi(x,t)dx
\end{eqnarray}
$$

The momentum probability density is $$\rho(p,t) = |\Phi(p,t)|^2 = \Phi^* \Phi$$, basically just like $$P$$ and $$\Psi$$. It follows the same normalization conditions too.

### Operators

If you calculate the expectation of momentum, you get

$$
\bar{p} = \left\langle p \right\rangle = \int \Psi^* \hat{p} \Psi dx
$$

where $$\hat{p} = -i\hbar \frac{\partial}{\partial x} = -i\hbar\nabla$$ is the **momentum operator**.

Now that we have the momentum operator, we can derive other operators based on it. These let us compute the expectation value of other quantities, such as:

- Kinetic energy: $$T = \frac{1}{2} mv^2 = \frac{p^2}{2m}$$, so $$\hat{T} = \frac{-\hbar^2\nabla^2}{2m}$$
- Angular momentum: $$\vec{L} = \vec{r} \times \vec{p}$$, so $$\hat{\vec{L}} = -i\hbar(\vec{r} \times \nabla)$$

In general, the expectation value of any dynamical quantity $$Q(x,p)$$ is $$\bar{Q}(x,p) = \left\langle Q(x,p) \right\rangle = \int \Psi^* Q(x, -i\hbar\nabla) \Psi dx$$.

### The uncertainty principle

$$
\sigma_x \sigma_p \geq \hbar / 2
$$

where $$\sigma_x = (\left\langle x^2 \right\rangle - \left\langle x \right\rangle ^2)^\frac{1}{2}$$, similar for $$\sigma_p$$.

### Separable solutions

Suppose that $$ \Psi(x,t) = \psi(x) \phi(t) $$. By the method of separation of variables, we can obtain

$$
\phi(t) = e^{-iEt/\hbar}
$$

for some constant $$ E $$. Let the Hamiltonian be

$$
H(x,p) = \frac{p^2}{2m} + V(x)
$$

be the total energy in the system (kinetic + potential), and let the Hamiltonian operator be

$$
\hat{H} = -\frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2} + V
$$

This lets obtain the time independent Schrödinger equation as:

$$
\hat{H} \phi = E \psi
$$

and has solutions $$ \Phi(x,t) = \phi{x} e^{iEt/\hbar} $$. These solutions are all stationary states ($$|\Psi|^2$$ doesn't change over time) and have definite total energy $$ E $$.

Also, **every** solution of the general Schrödinger equation can be written as a linear combination of these separable solutions.

## Solving the Schrödinger equation

### The infinite square potential well

- $$V(x) = 0$$ if $$ x \leq 0 \leq a $$, $$ \infty $$ otherwise.
- Solution: Let $$ k = \frac{\sqrt{2mE}{\hbar}} $$, $$ n \in \mathbb{Z}^+ $$. Then, solving TISE and normalizing, the separable solutions are $$ \psi_n(x) = \sqrt{\frac{2}{a}} \sin \left(\frac{n\pi x}{a}\right) $$.
- Note that $$ E = \frac{n^2 \pi^2 \hbar^2}{2ma^2} $$, so energy is quantized.
- Cool facts:
  1. $$ E_1 = \frac{\pi^2 \hbar^2}{2ma^2} $$ -- the minimal energy is more than zero. (Can understand through uncertainty principle)
  2. $$ E_n ~ n^2 $$. Can show this by considering $$ \Delta E $$ for some $$n$$. As $$ n \to \infty $$, $$ \frac{\Delta E_n}{E_n} \to 0 $$ and the energy is eventually like a continuum. This is Bohr's correspondence principle.
  3. $$ \psi_n(x) $$ are **mutually orthogonal**, i.e. $$ \int \psi^*_m(x) \psi_n(x) = \delta_{mn} $$ (the Kronecker delta). Can see by using trig rules.
  4. $$ \psi_n(x) $$ is **complete**. Any other function from 0 to a is a linear combination of the functions in that family.
