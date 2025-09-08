# IC basics

IC types by function: Analog (op-amps, 555, TL082, 565), Digital (gates, FFs, MUX/DEMUX, counters, ALU), Mixed-signal (ADC/DAC).

Complexity by gates/chip: SSI 3--30, MSI 30--300, LSI 300--3000, VLSI >3000.

# Op-amp block and model

Stages: input differential (high input resistance, most gain), intermediate differential (extra gain), level shifter (sets DC near 0 V), push--pull output (low output resistance, large swing).

Crossover distortion in push--pull fixed by ~2VBE bias.

Equivalent model: high input resistance, dependent source A-Vid, low output resistance to RL.

# Ideal vs practical DC

Ideal op-amp: A→∞, Ri→∞, Ro→0, BW→∞, CMRR→∞, slew→∞, Vio=0.

Input bias current: IB = (IB1 + IB2)/2.

Input offset current: Ios = IB1 - IB2.

Input offset voltage: Vios (small DC needed to make Vo=0).

Bias compensation (inverting amp): Rcomp = R1 || Rf at the non-inverting input.

Total output offset (inverting): Vo_off ≈ (1 + Rf/R1)-Vios + Rf-Ios; Rcomp reduces error.

Thermal drift units: Vios in µV/°C, IB/Ios in nA/°C.

PSRR: ΔVios/ΔVCC or ΔVios/ΔVEE.

CMRR: Ad/Acm.

# AC essentials

Key AC: frequency response, gain-bandwidth product (GBW), slew rate, rise time, settling time.

Distortion-free: slew rate ≥ max dVo/dt.

741: SR ≈ 0.5 V/µs; internally compensated; offset null pins 1 & 5.

# Core closed-loop amplifiers

Inverting amplifier: Av = -Rf/R1; Zin = R1; 180° phase inversion.

Non-inverting amplifier: Av = 1 + Rf/R1; unity buffer if Av = 1.

Inverting summer: Vo = -Rf Σ(Vi/Ri); equal Ri → Vo = -(Va + Vb + Vc).

Averager (inverting): choose Rf/R = 1/n to get Vo = -(sum)/n.

Non-inverting summer: set gain (1+Rf/R1) to number of inputs for sum; set to 1 for average.

Subtractor (difference amp): with R2/R1 = R4/R3, Vo = (R2/R1)(Vy - Vx).

# Instrumentation amplifier

Three op-amps: two non-inverting buffers with RG between, then a difference amp.

Overall gain: Ad = (R2/R1)-(1 + 2R/RG) where R are the equal series resistors.

Features: high gain accuracy, high CMRR, low drift, low offset, low output resistance.

# Differentiator

Ideal: Vo = -Rf C1 dVin/dt; |A| = ω Rf C1; noisy/unstable at high frequency.

Practical: add R1 in series with C1 and Cf across Rf.

Design: choose fa = highest needed; pick C1 < 1 µF → Rf = 1/(2π fa C1); set fb ≈ 20 fa → R1 = 1/(2π fb C1); choose Cf so R1C1 = RfCf.

Sine in → cosine out.

# Integrator

Ideal: Vo(t) = -(1/R1Cf) ∫ Vin dt + Vo(initial); Vo/Vin = -1/(s R1 Cf); slope -20 dB/dec.

Practical (lossy): add Rf ∥ Cf; Vo/Vin = -(Rf/R1)/(1 + s Rf Cf).

Square in → triangular out.

Comparator and zero-crossing detector

Inverting comparator: Vref at (+), Vin at (-); Vin > Vref → Vo = -Vsat; else +Vsat.

Zero-crossing detector: Vref = 0; outputs square wave on Vin sign changes.

Comparator notes: speed improved with positive feedback; logic-compatibility may need clamps/limiters.

Applications: zero/window detector, time marker, phase meter.

# Schmitt trigger (hysteresis)

Positive-feedback comparator; thresholds via R1--R2 and ±Vsat.

Upper threshold: VUT = (R1/(R1+R2))-(+Vsat).

Lower threshold: VLT = -(R1/(R1+R2))-Vsat.

Hysteresis: Vhy = 2(R1/(R1+R2))-Vsat.

Output: clean square for noisy/sine/saw inputs.

# Multivibrators (op-amp)

Astable: β = R2/(R1+R2); RC at (-) ramps until ±βVsat, then flips.

Period: T = 2RC ln((1+β)/(1-β)); if β = 0.5 → T = 2RC ln 3; Vo(pp) ≈ 2Vsat.

Monostable: one stable state; triggered via differentiator and diodes; pulse width:

T = RC ln((VD1 + Vsat)/((1-β)Vsat)); for R1 = R2 and Vsat ≫ VD1 → T ≈ 0.693 RC.

# Triangular wave generator

Comparator A1 drives integrator A2; divider R2--R3 sets switching thresholds.

Triangular amplitude: Vramp = (R2/R3)-Vsat; Vo(pp) = 2(R2/R3)-Vsat.

Frequency: fo = R3/(4 R1 C1 R2); increases with R3, decreases with R1, C1, R2.

# Sample and hold

EMOSFET switch controlled by Vc, hold capacitor C, output buffer A2.

Sample: Vc high → C tracks Vin; Hold: Vc low → C holds via buffer's high input impedance.

Uses: ADCs, DACs, demuxing, DVMs, data distribution, reconstruction filters.

# BITS quick hits

Differentiator: sine → cosine; Integrator: square → triangular; Schmitt trigger: square output; Integrator is low-pass in behavior.

Non-inverting gain Af = 1 + Rf/R1; inverting has 180° phase shift.

Stability via frequency compensation; gain falls at high frequency; GBW, SR, rise/settling are AC specs.

Distortion-free when SR ≥ max dVo/dt; 741 SR ≈ 0.5 V/µs; 741 internally compensated; offset null between pins 1 & 5.

Transimpedance: current-to-voltage; Transconductance: voltage-to-current; IC packages: DIP, TO, SMD.

Triangular generator frequency often given as f = 1/(4RC) in the provided configuration.
