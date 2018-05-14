# Synth Secrets

Notes on sound synthesis taken from Gordon Reid's series, [Synth
Secrets](http://sonicbloom.net/en/63-in-depth-synthesis-tutorials-by-sound-on-sound/).

## 1. What's in a sound?

- Plucking a string gives a fundamental, and several harmonics at integer
  multiple frequencies of the fundamental
- Basic waveforms:
  - Sine: only a fundamental
  - Sawtooth: nth harmonic has amplitude 1/n
  - Square: Sawtooth but only odd harmonics
- Subtractive synthesis: Starting with a sound rich in harmonics and filtering
  it

## 2. The physics of percussion

- Recall harmonic oscillators:
  - Sawtooth does brass, strings.
  - Square does clarinets.
  - Pulse waves (square with duty cycle): oboes, bassoons.
  - Sawtooth + pulse: base guitar.
  - "Suitably modified" sawtooth: lead guitar.
- Drums are non-harmonic
  - Circular drum skin: Involves Bessel function.
  - Atonal.
  - Don't even try to solve. Just filter noise.
- Metallic percussion (cymbals, bells, gongs)
  - Use a "ring modulator".

## 3. Modifiers and controllers

- Static sound/stationary sound: Unvarying tone
- Voltage control: Using voltage to control another thing
- Voltage controller amplifier (VCA): Using voltage to control amplification
- Envelope: Loudness contour for a sound (pointwise multiplication)
- Envelope generators are "triggered" to produce an envelope signal
- ADSR: Attack Decay Sustain Release.
  - Very common envelope generator
  - Attack, Decay, and Release are measures of time
  - Sustain is the sustain voltage level
  - "in many ways a stroke of genius" -- approximates many natural instruments
  - Organ envelope: Mostly rectangular ADSR
- LFO: Low-frequency oscillator
  - Generally 0.1 Hz to 20 Hz
  - Can be used for tremolo
- General terminology:
  - Signal generator: Source signal.
  - Modifier: Takes a source signal and some control signals and outputs a
    modified signal.
  - Controller: Signal that directs the modifier.
  - Many signal generators can also act as controllers

## 4. Of filters and phase relationships

- VCF: Voltage controlled filter. Nonlinear filter whose frequency response
  changes with time. The holy grail.
- Phase affects how waves mix
- A time delay shifts different frequencies by different amounts of phase
- Comb filter: Adding an offset signal to itself. Has a characteristic
  comb-shaped frequency response.
- Phase response can distort the shape of the resulting wave

## 5. Further with filters

- Passive filter: draws no power but the input signal
  - resistors, capacitors, inductors all passive
  - transistors, amplifiers are not
- Transfer function: output / input in frequency domain
- RC low-pass filter is first order
  - cutoff frequency is where 3dB is already lost
  - log frequency scale is useful for analyzing filter effect
  - want sharper cutoff -- not possible with passive filters
- (we dgaf about any of this because we're all digital, but it's good to know
  anyway)
- Active filter: filters with op amps to make them actually work

## 6. Of response and resonance

- RC lowpass:
  - Higher resistance -> lower cutoff frequency
- Band-pass filter: Low-pass and high-pass in series
- Resonance: Stuff is excited by sound at their resonant frequency
- Inductor can be used to simulate resonance
- Try boosting frequency near cutoff before the drop off for resonance
- Q: Parameter of resonant low-pass filter. Sharpness of resonance peak.
- Analog filter sweep: Sweeping cutoff frequency also sweeps resonance band
- Self-oscillation: Very large Q makes filter oscillate at the cutoff frequency
- Should be able to control both Q and cutoff through other input signals.
  Should figure out how to do this digitally (probably not that bad?)

## 7. Envelopes, gates, and triggers

- ADSR isn't the whole story
- Transient: another term for envelope
- Two AD generators can be multiplied to produce a cool 4-stage contour
- Analogue monosynth keyboards typically generate three signals per key press:
  - 1. Pitch CV: Determines pitch.
  - 2. Trigger: Short-duration pulse to activate things.
  - 3. Gate: Remains open for entire duration of keypress.
    - This tells the rest of the synth when you released the key.
- Trapezoid transient generator: Lin up to sustain on trigger, lin down to zero
  when gate released.
- EMS VCS3: Synth that has a Trapezoid
- ADSR transient generator: Attack and decay to sustain on trigger, release
  when gate released.
- Why not just use gate start as trigger? When multiple notes are played in
  quick succession, triggers allow subsequent notes to still have attack.
- Odyssey uses triggers. Minimoog does not. Odyssey sounds better.
- Reset-to-zero transient: Previous notes are instantly silenced when new key
  is pressed. Probably not what you want.
- Sometimes you want your transient to DEPEND on the frequency. E.g., pianos
  and guitars have quicker transients at higher frequencies. (I believe this is
  equivalent to a time-dependent frequency response, the holy grail.)
- Your brain uses the first few milliseconds of a sound to determine the
  instrument
- Initial flute waveform is filtered sawtooth + a little noise
- Minimoog has better flute solo than Odyssey for the same reason its
  keyboarding is worse

## 8. More about envelopes

- Lots of analog synths are limited because they only provide ADSR.
- ADSR is very limited.
- DAR: Delay, attack, release.
- ADSHR: Adds hold time (sustain extended after key is released)
- Yamaha GX1 ($60,000) had cool exponential ADSRs (you get exponentially closer
  to a certain level)
- DPA: Digital Parameter Access. Computation brings revolution to the signal
  world.
- DEG: Digital Envelope Generator. What we're making.
- Old computers used very few bits. We don't really have that problem anymore.
- People were really amazed at 5-stage envelopes...
- The lesson is: allow arbitrary interpolated envelopes.

## 9. An introduction to VCAs

- Recall: VCA is Voltage Controlled Amplifier
- They let you pointwise-multiply two arbitrary signals together, e.g. apply an
  envelope.
- Audio signals and control signals can be treated the same -- this is a very
  important idea.

## 10. Modulation

- Much more than using an LFO to add tremolo or vibrato.
  - Tremolo: Modulating amplitude.
  - Vibrato: Modulating frequency.
- Modulating filter cutoff:
  - 0.1 Hz: Slow filter sweep. Nice and ambient.
  - 1-2 Hz: Wah-wah
  - 10-20 Hz: Growl
- Modulating pulse wave duty cycle:
  - 5-10%: Thin, nasal. Oboes.
  - 11-49%: Thickens up
  - 50%: Distinctively hollow. Clarinets.
  - Harmonics: For a duty cycle of 1:n, every nth harmonic is missing from the
    spectrum.
- PWM: Pulse width modulation. Modulate the pulse wave duty cycle.
  - Creates a lush "chorused" sound.
  - Useful for synth string ensemble, synth lead.
  - Can also be applied to sawtooth.
- Foreshadowing: Modulating with audio signals results in drastically different
  effects.

## 11. Amplitude modulation

- Modulating amplitude with an LFO results in tremolo, but...
- Modulating amplitude with another audible signal "splits up" the original
  frequencies in the frequency domain, since:
      (a₁ + a₂ cos(ω₂t)) cos(ω₁t) 
    = a₁ cos(ω₁t) + ½ a₂ (cos((ω₁+ω₂)t + cos((ω₁-ω₂)t)))
  that is, the modulator frequency is added and subtracted from the carrier
  freuqnecy, and those become NEW frequencies in the resulting sound!
- This is an application of: pointwise multiplication in the time domain is
  convolution in the frequency domain.
- A ring modulator is just an amplitude modulator that only outputs the
  sum/difference frequencies
- Modulating filter cutoff with this technique just sweeps some harmonics in
  and out
- Next time: FM synthesis!

## 12. Frequency modulation (I)

- Discovered by John Chowning at Stanford
- Sold license to Yamaha and engineer Ichimura brought the synthesis world
  revolution.
- The FM synth equation:
    A₁ = a₁cos((ω₁+a₂cos(ω₂t))t)
- When ω₂ << ω₁, this is just vibrato
- FM synthesis is very very fast vibrato
- FM synthesis produces side bands of the form
    `ω_sb = ω_c ± nω_m`
  where `ω_c` is the carrier frequency, `ω_m` is the modulator frequency, n is
  an integer
- The modulation index `β = Δω_c / ω_m` determines the shape of the sidebands
- In a keyboard, to maintain consistent timbre, must scale carrier and
  modulating frequency in proportion
- Bandwidth of FM synth is approximately `B = 2ω_m(1+β)`.
- (!!!) Modulate the modulator frequency and get... VARYING BRIGHTNESS OVER
  TIME! One handle of the HOLY GRAIL!
- Next time: Practical FM synth, and operators.

## 13. Frequency modulation (II)

- C:M ratio: carrier:modulation ratio
- recall that side band frequencies are at C+kM, k integer
- call C±nM the nth order components
- then the amplitude of each pair of side bands is given by the Bessel
  function:
    `J(n,β) = sum for k from 0 to ∞ of (-1^k)(β/2)^(n+2k) / (k!(n+k)!)`
- positive side bands are added, negative side bands are subtracted
  - but they are shifted away from each other; with 1:1, it's 2 shift away
- terms get small real fast, often only need very small k
- "cross modulation" on analog synths often means frequency modulation
- 1:2 ratio gives side bands at C, 3C, 5C, ... -- a square wave!
- 1:3 is 33% pulse wave; 1:4 is similar to square wave
- operators
  - block diagrams become unwieldy fast; introduce "operator"
  - operators are oscillators + associated envelope generators, mixers, and
    VCAs
  - very useful to think of algorithms as diagrams of connected operators
  - cascading operators is modulating modulators
  - operators distribute (2,3->1 => 2->1 + 3->1)
- feedback
  - operators and operate on themselves, on in cycles
  - oh dang how to represent this
  - op1 -> op2 -> [2sines] -> feedback gives you noise (drums!)

## 14. Additive synthesis

- you can create sounds by adding a bunch of sine waves (thus point-specifying
  the frequency domain)
- Hammond Organ: nine integer harmonics
- Synth secret: Organs sound like organs because their sounds do not change
  over time.
  - Any timbre will sound organ-like if it doesn't change in time!
- How to make the sound more interesting?
  - Add time-varying filters and amplifiers. (now like a minimoog)
  - A real sound, like a plucked string, starts bright and goes darker over
    time.
      - Idea: time-varying amplifier BEFORE mixing the sines together.
      - Called Fourier synthesis.
- But we're still missing a piece. Flutes and trumpets have a component of
  time-varying filtered noise.
- Spectral Modelling Synthesis: You analyze a signal and then synthesize it
  with additive synthesis + noise

## 15. ESPS and vocoders
