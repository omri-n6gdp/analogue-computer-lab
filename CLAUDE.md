**-------------------------**
**PART I - PROJECT OVERVIEW**
**-------------------------**

Here is the fully updated and seamlessly integrated extraction document, preserving every detail from the initial extraction while incorporating the newly provided script terminal output.

**SECTION 1: EXPERIMENT OVERVIEW**
*   **Title of Experiment:** Project 2 Analogue Computer. Analogue Computer — Comprehensive Data Analysis (Y1 Lab Report).
*   **Aims and Objectives:** To build a real-time analogue computer to model a car's suspension. To determine the system's response to complex inputs such as a square or triangle wave. To simply easily adjust parameters (e.g. by changing resistors) and run a quick test with a variety of inputs without deriving a solution for each set of parameters and each waveform. To test the behaviour under a 'quasi-static' input, simulate a series of bumps in the road, and test amplitude and phase predictions to identify a resonance effect.
*   **Physical Phenomenon/System:** A mass-spring-damper system. The mass represents the body of the car (one-quarter of the car's total mass, i.e., the mass above each wheel). Connecting the mass to the wheel is a spring with a spring constant and a damper (shock absorber) with a damping constant. The spring supports the car body at a height y.
*   **Theoretical Context:** Operational Amplifier (op-amp) circuits can be built to perform the basic mathematical functions of addition, subtraction, integration, differentiation and scaling (multiplication by a constant). This is all that is needed to solve differential equations. Operational amplifiers were first developed to build analogue computers to perform these calculations. 
*   **GAPS:** No gaps identified. The sources provide a complete overview of the experiment.

**SECTION 2: THEORY AND DERIVATIONS**
*   Equation 1: $m\dot{y}=-f(t)-ky-b\dot{y}$.
    *   Variables: $m$ is mass (one-quarter of car's total mass), $y$ is height (equilibrium position $y=0$), $f(t)$ is an arbitrary force acting downwards on the body of the car, $k$ is spring constant, $b$ is damping constant.
    *   Assumptions: Forces are resolved in the upwards (+y) direction.
*   Equation: $f(t)=F_{0}cos(\omega t)$.
    *   Variables: $f(t)$ is the sinusoidal force, $F_{0}$ is amplitude, $\omega$ is angular frequency, $t$ is time.
*   Equation: $\tilde{y}(t)=Ae^{j(\omega t+\phi)}$.
    *   Variables: $\tilde{y}(t)$ is the steady-state solution, $A$ is the amplitude of the oscillation, $\phi$ is the phase.
    *   Assumptions: Steady-state solution for a sinusoidal applied force.
*   Equation 2: $\dot{y}=-\frac{f}{m}-\gamma\dot{y}-\omega_{0}^{2}y$.
    *   Variables: $\gamma=\frac{b}{m}$, $\omega_{0}^{2}=\frac{k}{m}$.
    *   Assumptions: Rearrangement of Equation 1.
*   Equation 3: $\zeta=\frac{b}{2\sqrt{mk}}$.
    *   Variables: $\zeta$ is the damping ratio.
    *   Limiting cases/conditions: For an under-damped response $\zeta<1$, for an over-damped response $\zeta>1$, for critical-damping $\zeta=1$.
*   Equation 4: $f_{r}=\frac{1}{2\pi\sqrt{ESL\times C}}$.
    *   Variables: $f_{r}$ is self-resonance frequency, $ESL$ is equivalent series inductance, $C$ is capacitance.
    *   Conditions: This is the frequency where the impedance $|Z(f)|$ reaches a minimum.
*   Equation 5: $|Z(f)|=\sqrt{ESR^{2}+(2\pi f\times ESL-\frac{1}{2\pi fC})^{2}}$.
    *   Variables: $|Z(f)|$ is frequency-dependent impedance, $ESR$ is equivalent series resistance, $f$ is frequency, $ESL$ is equivalent series inductance, $C$ is capacitance.
*   Equation 6: $Z_{tot}=R_{o}+R_{p}=10~M\Omega$, $r_{eff}=\frac{R_{o}}{R_{o}+R_{p}}=\frac{1}{10}$.
    *   Variables: $Z_{tot}$ is input impedance of the probe at frequencies between DC and 1 kHz, $R_{o}$ is oscilloscope input impedance ($1~M\Omega$), $R_{p}$ is probe tip resistor ($9~M\Omega$), $r_{eff}$ is resistive division factor.
*   Equation 7: $r_{eff}=\frac{R_{o}}{R_{o}+R_{p}}=\frac{C_{p}}{C_{adj}+C_{cable}+C_{p}+C_{o}}=\frac{1}{10}$.
    *   Variables: $C_{p}$ is probe capacitor ($9.5~pF$), $C_{adj}$ is adjustable compensation capacitance, $C_{cable}$ is coaxial cable capacitance, $C_{o}$ is oscilloscope capacitance to ground.
    *   Conditions: Valid at higher frequencies where input impedance is dominated by the effect of the capacitor $C_{p}$.
*   Equation: $\tau_1 = R_4 C_1$.
*   Equation: $\tau_2 = R_3 C_2$.
*   Equation: $e_{\tau} = \sqrt{e_R^2 + e_C^2}$.
*   Equation: $K = 1 + (R_7 / R_8)$.
*   Equation: $e_{divider\_frac} = \sqrt{e_R^2 + e_R^2}$.
*   Equation: $e_{K\_frac} = \frac{R_7 / R_8}{K} \times e_{divider\_frac}$.
*   Equation: $\omega_{0}^{2} = \frac{R_1 K}{R_9 \tau_1 \tau_2}$.
*   Equation: $e_{\omega_0\_sq\_frac} = \sqrt{e_R^2 + e_{K\_frac}^2 + e_R^2 + e_{\tau}^2 + e_{\tau}^2}$.
*   Equation: $e_{\omega_0\_frac} = 0.5 \times e_{\omega_0\_sq\_frac}$.
*   Equation: $\omega_0 = \sqrt{\omega_{0}^{2}}$.
*   Equation: $f_{0\_theo} = \frac{\omega_0}{2 \pi}$.
*   Equation: $e_{\gamma\_frac} = \sqrt{4 e_R^2 + e_{\tau}^2}$.
*   Equation: $\gamma_{light} = \frac{R_1 R_5}{R_2 R_{6\_light} \tau_1}$.
*   Equation: $\gamma_{crit} = \frac{R_1 R_5}{R_2 R_{6\_crit} \tau_1}$.
*   Equation: $\gamma_{heavy} = \frac{R_1 R_5}{R_2 R_{6\_heavy} \tau_1}$.
*   Equation: $e_{\zeta\_frac} = \sqrt{e_{\gamma\_frac}^2 + e_{\omega_0\_frac}^2}$.
*   Equation: $\zeta_{light\_theo} = \frac{\gamma_{light}}{2 \omega_0}$.
*   Equation: $\zeta_{crit\_theo} = \frac{\gamma_{crit}}{2 \omega_0}$.
*   Equation: $\zeta_{heavy\_theo} = \frac{\gamma_{heavy}}{2 \omega_0}$.
*   Equation: $e_{G\_frac} = \sqrt{e_R^2 + e_R^2}$.
*   Equation: $V_{in} = f/m$.
*   Equation (step_response, $\zeta < 1.0$): $y_{ss} + (y_0 - y_{ss}) \times \exp(-\zeta \omega_n dt) \times (\cos(\omega_d dt) + (\frac{\zeta}{\sqrt{1 - \zeta^2}}) \times \sin(\omega_d dt))$ where $\omega_d = \omega_n \sqrt{1 - \zeta^2}$.
*   Equation (step_response, $\zeta == 1.0$): $y_{ss} + (y_0 - y_{ss}) \times (1 + \omega_n dt) \times \exp(-\omega_n dt)$.
*   Equation (step_response, $\zeta > 1.0$): $y_{ss} + (y_0 - y_{ss}) \times \frac{s_2 \exp(s_1 dt) - s_1 \exp(s_2 dt)}{s_2 - s1}$ where $s_1 = -\omega_n (\zeta - \sqrt{\zeta^2 - 1})$ and $s_2 = -\omega_n (\zeta + \sqrt{\zeta^2 - 1})$.
*   Equation (bode_amp_func): $\frac{G}{\sqrt{(1 - r^2)^2 + (2 \zeta r)^2}}$ where $r = f / f_0$.
*   Equation (bode_phase_func): $\text{degrees}(\arctan2(2 \zeta r, 1 - r^2)) - 180$ where $r = f / f_0$.
*   Equation (damped_osc_func): $C + A \times \exp(-\beta t) \times \cos(\omega_d t + \phi)$.
*   Equation: $\chi^2_{\nu} = \frac{\sum (\frac{y_{data} - y_{fit}}{\sigma})^2}{n_{dof}}$.
*   Equation: $f_{peak\_theo} = f_{0\_theo} \sqrt{1 - 2 \zeta_{light\_theo}^2}$.
*   Equation: $f_{d\_theo} = f_{0\_theo} \sqrt{1 - \zeta_{light\_theo}^2}$.
*   Equation: $R = 2 m \omega_0 \zeta$.
*   Equation: $V_{ss\_theo} = -G_{DC} V_{in}$ where $G_{DC} = \frac{R_1}{R_{10}}$.
*   **GAPS:** Derivation steps to convert Eq 1 into Eq 2 are stated as "re-arrange" without showing the intermediate algebra. The full derivation of the block diagram transfer functions is left as an exercise for the student.

**SECTION 3: APPARATUS AND EQUIPMENT**
*   Signal generator: Provides the driving force $f(t)$ as a voltage.
*   LT1001 precision op-amps: Used for scaling, integration, and summation. Gain-bandwidth product is 0.8 MHz.
*   100 µF non-polarised (NP) capacitors: Used for the integrators.
*   10 µF capacitors: Placed between $+V_{ss}$ pin and ground, and $-V_{ss}$ pin and ground as local energy reservoirs (decoupling) to reduce oscillation and noise.
*   100 nF ceramic capacitors: Placed in parallel with the 10 µF capacitors to provide low impedance damping of noise at higher frequencies.
*   Power supplies: Set to +15 V or +5 V, and -15 V or -5 V.
*   Oscilloscope: Used to measure voltages. Input impedance is $1~M\Omega$ and $10-20~pF$.
*   10x Passive oscilloscope probes: Mitigates stray impedance loads. Contains a $9~M\Omega$ resistor and $9.5~pF$ capacitor. Features a selector switch and an adjustable equalization circuit screw T1.
*   Banana cables and BNC coaxial cables: Used to connect circuits to oscilloscope.
*   Bread board: Used to build the circuit.
*   Wires: Used for connections.
*   Resistors: 10 kΩ, 33 kΩ, 12 kΩ, 2.2 kΩ, 1 kΩ, 82 kΩ, 1.5 kΩ.
*   4.7 µF capacitor: Placed in parallel across input resistor R10 to simulate an impulse.
*   LCR bridge: Used to accurately measure actual resistor and capacitor values.
*   **GAPS:** Specific brand/model numbers for the signal generator, oscilloscope, LCR bridge, and power supplies are not documented.

**SECTION 4: SAFETY AND RISK**
*   "Safety Note: As our signals may be in general positive or negative, it's important to use non-polarised capacitors (identified with 'NP') for this project.".
*   "Polarised capacitors connected wrongly can explode, so only use the NP type supplied in the project kit, and don't replace with any unknown capacitor types you might find in the lab.".
*   "As a further safety measure, set the current limit function on each power supply. 20 mA will be sufficient for this circuit.".
*   "kept short circuiting and limiting the current on the negative power supply... ensured each op amp was still fully functional after shorting by testing a standard input... Checked capacitors were also not blown and that no component was getting very hot.".
*   "To measure the circuit, we first discharged the capacitors by touching their two ends together with a wire.".
*   **GAPS:** No mention of standard electrical hazards (e.g., bare wires, grounding, liquids) beyond the capacitor polarity warnings.

**SECTION 5: EXPERIMENTAL METHOD AND PROCEDURE**
*   **Manual Steps:**
    1.  Predict the output voltage for the maximum static input.
    2.  Implement the circuit in LTSpice, using LT1001 precision op-amps, and use this to refine the overall design.
    3.  Check that the outputs of all the op-amps remain within the allowable voltage range.
    4.  Simulate the static response of the system by setting a voltage source to pulse on from zero to 5 volts.
    5.  Build the circuit using LT1001 precision op-amps with 100 µF non-polarised capacitors for integrators.
    6.  Place 10 µF and 100 nF decoupling capacitors close to the power $+V_{ss}$ and $-V_{ss}$ pins.
    7.  Analyze phase-shifts of the circuit using LTSpice if it oscillates, to ensure no $180^{\circ}$ phase shifts.
    8.  Connect the BNC connector of the passive probe to an oscilloscope input channel and adjust vertical scale to 10:1.
    9.  Set the selector switch on the body of the probe to '10x'.
    10. Connect the probe and its ground alligator clip to the 'Probe Comp.' terminals on the front panel.
    11. Adjust the screw T1 on the BNC connector side of the probe until a sharp rectangular waveform is observed.
    12. Apply a square wave, at very low frequency, to test the behaviour under a 'quasi-static' input and check correct static response.
    13. Apply a square wave at higher frequencies, with reasonable amplitude, to simulate a series of bumps.
    14. Apply a sinusoidal input at varying frequencies to test amplitude and phase predictions and identify a resonance effect.
    15. Try changing the damping ratio $\zeta$.
*   **Lab Book Steps & Deviations:**
    1.  First created circuit schematic on LTSpice.
    2.  Built circuit on bread board.
    3.  Circuit was "Very sensitive... kept short circuiting and limiting the current". *Deviation/Difficulty flagged.*
    4.  Replaced wires until circuit was no longer shorting.
    5.  "Very noisy output, decided to rearrange circuit and rail positioning to allow for shorter wires overall, however this was not always possible...". *Difficulty flagged.*
    6.  Fixed phase flipping issue by "resetting the oscilloscope and changing output channels". *Difficulty flagged.*
    7.  Discharged capacitors by touching their two ends together with a wire.
    8.  Tested the impact of adding 100nF and 10uF decoupling capacitors between + and - Vss pins and ground.
    9.  Calibrated probe by adjusting the screw on the BNC connector until a sharp rectangular waveform was achieved.
    10. Modeled a static pulse by outputting a square wave with a 5-second frequency (0V to 2.18V).
    11. Performed a frequency sweep taking data from 0.1Hz to 2Hz in increments of 100mHz, then recorded 2.5Hz and 3Hz.
    12. Ran a sample acquisition over "many wave counts" to get a mean and standard deviation.
    13. Phase offset: "took all our phase offsets as negative, subtracting 360 where needed".
    14. Changed R6 from 12 kOhm to 2.2 kOhm to get critical damping.
    15. Changed R6 to 1 kOhm for heavy damping.
    16. Recorded waveforms for 1.1Hz, 1.2Hz and 1.3Hz for all three damping types.
    17. Added a 4.7 uF capacitor in parallel across input resistor R10 to simulate an impulse generated when there is a sudden change in road height. *Deviation from manual.*
*   **GAPS:** Exact sampling rates used on the oscilloscope are not recorded. The exact amplitude of the input sine wave during the frequency sweeps is not explicitly stated in the method steps.

**SECTION 6: RAW DATA AND OBSERVATIONS**
*   **From Manual:**
    *   Parameter Table 1: Spring constant $k = 20040~N/m$, Damping constant $b = 990~Ns/m$, Mass (quarter car) $m = 360~kg$.
*   **From Lab Book:**
    *   Initial LTSpice output showed significant damping with pi/2 (90) phase shift to the right, output lagged input.
    *   Uncertainty on input signal: $\sim \pm 5mV$ on 100mV input, probably closer to $\pm 1mV$.
    *   Output noise statistics (10x probe): mean = 10.519mV, std = 0.52803mV.
    *   Components have $\pm 5\%$ uncertainty.
    *   Calculated $\omega_{0}^{2} = 55.667 \pm 3.87$.
    *   Calculated $\gamma = 2.75 \pm 0.194$.
    *   Calculated resonance = 1.177 Hz.
    *   Input voltage of 1V = $1~m/s^2$ acceleration.
    *   Output of 1V = $1~m$ displacement.
    *   $V_{in}$ for weight of 1 person (80kg) = 2.18V.
    *   LTSpice step simulation gave a displacement of -39mV.
    *   Decoupling capacitors reduced noise uncertainty from $\pm 10mV$ to $\pm 8mV$.
    *   High frequency square wave input resulted in a very constant output.
    *   Critical damping constant calculated as 14.9.
*   **From Script (Hardcoded/Measured Data):**
    *   m = 360.0.
    *   Resistors: R1 = 9890.0, R2 = 9880.0, R3 = 9890.0, R4 = 9840.0, R5 = 32900.0, R6_light = 11900.0, R6_crit = 2180.0, R6_heavy = 980.0, R7 = 80800.0, R8 = 1480.0, R9 = 9890.0, R10 = 9990.0.
    *   Capacitors: C1 = 97.4e-6, C2 = 97.3e-6.
    *   LCR tolerances: $e_R = 0.001$, $e_C = 0.0014$.
*   **From Script Terminal Output (Dynamic-Range Flags & Noise Data):**
    *   Light Damping: N = 22, amp_lowSNR(<20mV) = 0, amp_warn(<10mV) = 0, phase_warn(StdDev>15°) = 1, low_wave_count(<20) = 0.
    *   Critical Damping: N = 20, amp_lowSNR(<20mV) = 0, amp_warn(<10mV) = 0, phase_warn(StdDev>15°) = 2, low_wave_count(<20) = 3.
    *   Heavy Damping: N = 20, amp_lowSNR(<20mV) = 4, amp_warn(<10mV) = 2, phase_warn(StdDev>15°) = 15, low_wave_count(<20) = 4.
    *   Step response: noise $\sigma = 1.723~mV$, $N = 10948$.
    *   Impulse response: noise $\sigma = 2.741~mV$, $N = 38126$.
*   **Discarded/Suspect Data:**
    *   "The input signal of the oscilloscope kept flipping phase, so when we took an average of the output, it went to zero as the amplitudes cancel" (Data inherently discarded via fixing the setup by resetting scope).
*   **GAPS:** The full array of raw frequency sweep values (amplitudes, phases, and frequencies) actually collected during the 0.1Hz-3Hz sweep is missing from the sources, though it is referenced by the script.

**SECTION 7: DATA ANALYSIS AND CALCULATIONS**
*   **Lab Book Methods:**
    *   Integrators have gain 1.
    *   "changing the resistors from 10kohm to 1kohm, increasing our output voltage by a factor of 100".
*   **Python Script Pipeline & Functions:**
    *   **Libraries:** numpy, pandas, matplotlib.pyplot, matplotlib.lines, matplotlib.patches, scipy.optimize.curve_fit, os.
    *   **Constants & Thresholds:** `SCOPE_AMP_FLOOR = 0.01`, `SCOPE_PHASE_FLOOR = 0.5`, `NOISE_FLOOR_AMP = 0.005`, `LOW_AMP_THRESHOLD = 0.020`, `WARN_AMP_THRESHOLD = 0.010`, `WARN_PHASE_STDDEV = 15.0`, `t0_i = 5.0`.
    *   `_find_file(folder, filename)`: Performs case-insensitive lookup to find files.
    *   `load_waveform(filepath)`: Loads CSV, renames 'in s' to 'time', 'C1 in V' to 'input', 'C3 in V' to 'output'.
    *   `stats_file(filepath)`: Parses a scope statistics CSV. Calculates per-frequency uncertainty: `sigma_total = sqrt( sigma_stat^2 + sigma_syst^2 )`. Gain is `amp_out / amp_in`. Inflates `amp_out_err` using `NOISE_FLOOR_AMP` if `amp_out < LOW_AMP_THRESHOLD` or if `amp_out_stddev == 0.0`. Never drops points.
    *   `load_sweep(folder)`: Loads all CSVs from a folder, sorts by frequency, returns DataFrame. Raises Key/FileNotFound errors if missing.
    *   `step_response(t, y_ss, y_0, zeta, wn)`: Computes analytical step response based on damping regime (under/crit/over).
    *   `bode_amp_func(f, f0, zeta, G)`: Formula: $G / \sqrt{(1 - r^2)^2 + (2 \zeta r)^2}$.
    *   `bode_phase_func(f, f0, zeta)`: Formula: $\text{degrees}(\arctan2(2 \zeta r, 1 - r^2)) - 180$.
    *   `damped_osc_func(t, A, beta, wd, phi, C)`: Formula: $C + A \times \exp(-\beta t) \times \cos(\omega_d t + \phi)$.
    *   `reduced_chi2(y_data, y_fit, sigma, n_params)`: Formula: `sum((resid / sigma)**2) / n_dof`.
    *   `add_systematic(value, stat_err, frac_syst)`: Formula: `sqrt(stat_err**2 + (value * frac_syst)**2)`.
    *   `noise_sigma(data_array, n_samples)`: Returns standard deviation of first `n_samples`.
    *   `unwrap_phase(phase_deg, freq, f0, zeta_ref)`: Resolves 360-degree ambiguities by comparing candidates ($ph, ph+360, ph-360$) against `bode_phase_func`.
    *   `filter_drop(df, drop_col, fmax)`: Returns rows where `freq <= fmax`.
    *   `fit_bode_amp_free`, `fit_bode_amp_fixed_f0`, `fit_phase_free`, `fit_phase_fixed_f0`: Uses `scipy.optimize.curve_fit` with `absolute_sigma=True`. Computes parameters, errors, and chi-squared.
    *   `step_wrapper(t, y_ss, y0, z, wn)`: Evaluates `step_response` over an array.
*   **Uncertainty Propagation formulas (implemented in code):**
    *   $e_{\tau} = \sqrt{e_R^2 + e_C^2}$.
    *   $e_{K\_frac} = ((R_7 / R_8) / K) \times \sqrt{e_R^2 + e_R^2}$.
    *   $e_{\omega_0\_sq\_frac} = \sqrt{e_R^2 + e_{K\_frac}^2 + e_R^2 + e_{\tau}^2 + e_{\tau}^2}$.
    *   $e_{\gamma\_frac} = \sqrt{4 e_R^2 + e_{\tau}^2}$.
    *   $e_{\zeta\_frac} = \sqrt{e_{\gamma\_frac}^2 + e_{\omega_0\_frac}^2}$.
    *   $e_{G\_frac} = \sqrt{e_R^2 + e_R^2}$.
    *   `gain_err = gain * sqrt((amp_out_err / amp_out)**2 + (amp_in_err / amp_in)**2)`.
*   **Processing Pipeline:** Loads sweep data -> fits Bode amplitude (free for light, fixed $f_0$ for crit/heavy) -> fits Bode phase independently with phase unwrapping -> loads and fits static step response -> loads and fits impulse response -> calculates combined stats+syst uncertainties -> prints formatted report -> generates 4 main data plots -> generates 4 residual plots.
*   **GAPS:** No gaps identified regarding the described analysis procedures.

**SECTION 8: RESULTS**
*   **Lab Book Results:**
    *   "Our real circuit matches both our predictions and the ltspice simulations.".
    *   Real circuit displacement matches simulation at -39mV.
*   **Script Terminal Output Results (Comprehensive Fit Data):**
    *   **Natural frequency:**
        *   $\omega_0$ (Bode amp light): Theo = $7.7640 \pm 0.0122~rad/s$, Exp = $6.9690 \pm 0.0029(stat) \pm 0.0109(sys)~rad/s$, $\Delta = 47.84~\sigma$.
        *   $f_0$ (Bode amp light): Theo = $1.2357 \pm 0.0019~Hz$, Exp = $1.1092 \pm 0.0005(stat) \pm 0.0017(sys)~Hz$, $\Delta = 47.84~\sigma$.
        *   $f_0$ (Bode phase light): Theo = $1.2357 \pm 0.0019~Hz$, Exp = $1.1058 \pm 0.0011(stat) \pm 0.0017(sys)~Hz$, $\Delta = 45.91~\sigma$.
        *   $f_0$ (step response): Theo = $1.2357 \pm 0.0019~Hz$, Exp = $1.1200 \pm 0.0077(stat) \pm 0.0018(sys)~Hz$, $\Delta = 14.25~\sigma$.
        *   $f_0$ (impulse $\sqrt{\beta^2+\omega_d^2}$): Theo = $1.2357 \pm 0.0019~Hz$, Exp = $1.1045 \pm 0.0003(stat) \pm 0.0017(sys)~Hz$, $\Delta = 50.04~\sigma$.
    *   **Damping ratio $\zeta$:**
        *   $\zeta$ light (amp fit): Theo = $0.1860 \pm 0.0006$, Exp = $0.1980 \pm 0.0004(stat) \pm 0.0006(sys)$, $\Delta = 13.27~\sigma$.
        *   $\zeta$ light (phase fit): Theo = $0.1860 \pm 0.0006$, Exp = $0.1999 \pm 0.0017(stat) \pm 0.0006(sys)$, $\Delta = 7.33~\sigma$.
        *   $\zeta$ light (impulse): Theo = $0.1860 \pm 0.0006$, Exp = $0.1975 \pm 0.0003(stat) \pm 0.0006(sys)$, $\Delta = 13.23~\sigma$.
        *   $\zeta$ critical (amp fit): Theo = $1.0151 \pm 0.0031$, Exp = $1.0305 \pm 0.0112(stat) \pm 0.0032(sys)$, $\Delta = 1.28~\sigma$.
        *   $\zeta$ critical (phase fit): Theo = $1.0151 \pm 0.0031$, Exp = $1.2771 \pm 0.0688(stat) \pm 0.0039(sys)$, $\Delta = 3.80~\sigma$.
        *   $\zeta$ critical (step): Theo = $1.0151 \pm 0.0031$, Exp = $1.0299 \pm 0.0072(stat) \pm 0.0032(sys)$, $\Delta = 1.75~\sigma$.
        *   $\zeta$ heavy (amp fit): Theo = $2.2581 \pm 0.0069$, Exp = $2.0758 \pm 0.0521(stat) \pm 0.0064(sys)$, $\Delta = 3.44~\sigma$.
        *   $\zeta$ heavy (phase fit): Theo = $2.2581 \pm 0.0069$, Exp = $3.2095 \pm 0.2970(stat) \pm 0.0099(sys)$, $\Delta = 3.20~\sigma$.
    *   **Damping coefficient R:**
        *   R light: Theo = $1039.5293 \pm 2.7425~Ns/m$, Exp = $1107.0293 \pm 2.0400(stat) \pm 3.8163(sys)~Ns/m$, $\Delta = 13.18~\sigma$.
        *   R critical: Theo = $5674.4947 \pm 19.5621~Ns/m$, Exp = $5760.3164 \pm 62.3516(stat) \pm 19.8579(sys)~Ns/m$, $\Delta = 1.26~\sigma$.
        *   R heavy: Theo = $12622.8556 \pm 43.5156~Ns/m$, Exp = $11603.6308 \pm 291.2304(stat) \pm 40.0020(sys)~Ns/m$, $\Delta = 3.43~\sigma$.
    *   **Resonance & damped frequency:**
        *   $f_{peak}$ (light): Theo = $1.1922 \pm 0.0019~Hz$, Exp = $1.0648 \pm 0.0005(stat) \pm 0.0017(sys)~Hz$, $\Delta = 49.66~\sigma$.
        *   $f_d$ (impulse): Theo = $1.2141 \pm 0.0019~Hz$, Exp = $1.0827 \pm 0.0003(stat) \pm 0.0017(sys)~Hz$, $\Delta = 50.97~\sigma$.
        *   $\omega_d$ (impulse): Theo = $7.6286 \pm 0.0120~rad/s$, Exp = $6.8028 \pm 0.0021(stat) \pm 0.0107(sys)~rad/s$, $\Delta = 50.97~\sigma$.
    *   **Impulse-response parameters:**
        *   $\beta$ (decay rate): Theo = $1.4438 \pm 0.0038~s^{-1}$, Exp = $1.3706 \pm 0.0018(stat) \pm 0.0036(sys)~s^{-1}$, $\Delta = 13.15~\sigma$.
        *   $t_{1/2}$: Theo = $0.4801 \pm 0.0013~s$, Exp = $0.5057 \pm 0.0007(stat) \pm 0.0013(sys)~s$, $\Delta = 13.07~\sigma$.
    *   **Static / DC values:**
        *   $V_{ss}$: Theo = $-38.8000 \pm 0.0549~mV$, Exp = $-42.4657 \pm 0.0247(stat) \pm 1.0601(sys)~mV$, $\Delta = 3.45~\sigma$.
        *   DC gain G (light): Exp = $0.0176 \pm 0.0000(stat) \pm 0.0000(sys)~V/V$.
        *   DC gain G (critical): Exp = $0.0172 \pm 0.0001(stat) \pm 0.0000(sys)~V/V$.
        *   DC gain G (heavy): Exp = $0.0169 \pm 0.0002(stat) \pm 0.0000(sys)~V/V$.
    *   **Goodness of fit ($\chi^2_\nu$):**
        *   Bode amplitude (Light): $\chi^2_\nu = 6.549$ (dof = 17, N = 20) (off).
        *   Bode amplitude (Critical): $\chi^2_\nu = 5.375$ (dof = 18, N = 20) (off).
        *   Bode amplitude (Heavy): $\chi^2_\nu = 65.548$ (dof = 17, N = 19) (off).
        *   Bode phase (Light): $\chi^2_\nu = 6.313$ (dof = 18, N = 20) (off).
        *   Bode phase (Critical): $\chi^2_\nu = 4.759$ (dof = 19, N = 20) (off).
        *   Bode phase (Heavy): $\chi^2_\nu = 0.902$ (dof = 18, N = 19) (✓).
        *   Step response: $\chi^2_\nu = 0.571$ (dof = 10944, N = 10948) (✓).
        *   Impulse response: $\chi^2_\nu = 0.334$ (dof = 38121, N = 38126) (off).
*   **GAPS:** The plots generated by the script are still missing from the provided sources.

**SECTION 9: REPORT REQUIREMENTS**
*   **Weighting:** Forms 85% of the mark for the course.
*   **Effort:** Individual effort; each student submits a personal report.
*   **Format:** Use the template for year 1 lab reports.
*   **Length:** Up to 4 pages long (including graphs, figures, vital appendices). Bibliography, circuit photograph, and acknowledgements can spill to the 5th page.
*   **Required Sections:** Abstract, conclusions, bibliography, and a photograph of the circuit in the Appendix.
*   **Content Rules:**
    *   Concisely describe the project's objectives.
    *   Demonstrate a precise understanding of the principles.
    *   Show a thorough evaluation of the performance.
    *   Compare with theory and/or simulation as appropriate.
    *   Reference anything you use (text, figures, results not created by yourself).
    *   Include uncertainty information contextually (reader must be able to judge results against uncertainties).
*   **Submission:** Turnitin, before the deadline of 10 a.m. on Tuesday 5th May.
*   **Rubric (100 points standard + 30 points addendum = 130 total):**
    *   Abstract: 5 points.
    *   Introduction and Theory: 15 points.
    *   Methods: 20 points.
    *   Figures (Intro, theory, methods): 10 points.
    *   Results (Data presentation): 20 points.
    *   Discussion: 25 points.
    *   Conclusion: 5 points.
    *   Depth of understanding: 10 points (Mastering = physics correct, sufficient, complete without unnecessary derivations).
    *   Achievement: 10 points (Mastering = circuit fully working and thoroughly described/evaluated).
    *   Independent thought: 10 points (Mastering = imaginative research question, original method fully explained).
*   **GAPS:** No explicit font size, margin, or line-spacing formatting requirements are listed.

**SECTION 10: CROSS-SOURCE CONSISTENCY LOG**
*   **Parameter m:** states 360 kg. states 360 kg. states 360.0. **Status: Agree.**
*   **Parameter k:** states 20040 N/m. states 20040 N/m. **Status: Agree.**
*   **Parameter b:** states 990 Ns/m. states 990 Ns/m. **Status: Agree.**
*   **Integrator Capacitors (C1, C2):** states 100 µF. text states 100uF NP, but LTSpice diagram label says 0.0001F (which is 100uF). defines exact measured values C1 = 97.4e-6 F and C2 = 97.3e-6 F. **Status: Partially agree** (Script reflects highly precise LCR measurements of the nominal 100uF capacitors).
*   **Damping Resistor (R6):** states 12kOhm for light, 2.2kOhm for critical, 1kOhm for heavy. states R6_light = 11900.0, R6_crit = 2180.0, R6_heavy = 980.0. **Status: Partially agree** (Script reflects highly precise LCR measurements of the nominal resistors).
*   **Resonance Frequency:** calculates resonance as $1.177~Hz$. Script terminal output calculates theoretical $f_0 = 1.2357~Hz$ and experimental $f_0 \approx 1.1092~Hz$. **Status: Conflict.**
*   **Static Pulse Input Voltage:** states the weight of 1 person (80kg) results in $V_{in} = 2.18V$. logic calculates $V_{in}$ dynamically from CSV, but provides a hardcoded fallback $V_{in} = -0.0388 V$ (`V_ss_theo_V = -0.0388`). **Status: Conflict.**
*   **Static Pulse Output Voltage:** states displacement prediction and LTSpice simulation is -39mV. fallback variable `V_ss_theo` is -38.8mV. Script terminal output shows experimental $V_{ss}$ as $-42.4657~mV$. **Status: Partially agree** (Simulation vs experimental reality).

**SECTION 11: GAPS AND MISSING INFORMATION**
*   **Missing Theory:** The explicit algebraic steps to rearrange Equation 1 into Equation 2 are omitted. The transfer functions and block-diagram nodal derivations are expected by the manual but not provided.
*   **Missing Method Detail:** The exact sample rate / time-base used on the oscilloscope during data capture is not documented. The amplitude of the sine wave used for the frequency sweep is not recorded.
*   **Missing Data:** The raw numerical CSV data from the frequency sweeps (Light_FreqSweep, Critical_FreqSweep, Heavy_FreqSweep) and time-domain waveforms (Rect_Output.CSV, Impulse_Waveform.CSV) are entirely absent.
*   **Missing Results:** While the script's numerical output table has now been provided, the physical plots generated by the python script (e.g., Plot1_Static_Response.png, Plot2_Bode_Amplitude.png, and the residual plots) are completely missing.
*   **Missing Equipment Specifications:** The specific models/brands of the signal generator, oscilloscope, LCR bridge, and power supplies are not stated.
*   **Missing Safety Information:** Standard laboratory safety protocols (e.g., handling liquids, grounding oneself) are not detailed.

**-------------------------------------**
**PART II - WRITING STYLE AND STRUCTURE**
**-------------------------------------**

## SECTION 1: OVERALL DOCUMENT STRUCTURE
*   **Format and Styling:** The author consistently uses a formal, two-column academic article format across all reports, indicated by the use of capitalised, Roman-numeral headings (e.g., "I. INTRODUCTION", "II. THEORY")[cite: 5, 6, 7].
*   **Section Order:** The high-level section progression is highly standardised: Abstract, Introduction, Theory, Methods, Results/Discussion, Conclusion, Acknowledgments, References[cite: 5, 6, 7].
*   **Variations in Sectioning:** 
    *   The "Abstract" is numbered "I. ABSTRACT" in two of the three reports[cite: 5, 6], but left as an unnumbered heading in one[cite: 7]. 
    *   The Results and Discussion sections are separated into "V. RESULTS" and "VI. DISCUSSION" in one report[cite: 5], but merged into a single "V. RESULTS & DISCUSSION" or "IV. RESULTS & DISCUSSION" in the other two[cite: 6, 7].
    *   The order of the final two sections fluctuates: Acknowledgments precede References in two reports[cite: 5, 6], but References precede Acknowledgments in the third[cite: 7].

## SECTION 2: SECTION-BY-SECTION INTERNAL STRUCTURE
*   **Abstract:** Consistently 1 paragraph[cite: 5, 6, 7]. Always opens by stating the core objective or action, e.g., "The thickness of a soap bubble was measured..."[cite: 5] or "The aim of this experiment was to determine..."[cite: 6, 7]. Internally organised to present the final quantitative result with uncertainty, the percentage deviation from the accepted value, and a concluding sentence summarising the dominant source of error or the overarching physical demonstration[cite: 5, 6, 7].
*   **Introduction:** Typically 2-3 paragraphs[cite: 5, 6, 7]. Opens with a broad statement about the general physical field (e.g., "INTERFEROMETRY provides a precise..."[cite: 5], "SPECTROSCOPY is the study of..."[cite: 6], "PENDULUMS are used in..."[cite: 7]). Progresses to the specific application, and always closes by explicitly stating the aim of the present experiment (e.g., "The aim of this experiment was to measure..."[cite: 6]).
*   **Theory:** Opens by defining the core physical principle or model (e.g., "This experiment is based on the physical principle of superposition..."[cite: 5], "A stiff pendulum is a rigid body which oscillates..."[cite: 7]). Progresses by introducing equations sequentially and defining their variables.
*   **Methods:** Consists of 2-4 paragraphs describing the apparatus, the procedural steps, and the data processing techniques[cite: 5, 6, 7]. Often incorporates a diagram of the experimental setup near the beginning[cite: 5, 6, 7]. 
*   **Results & Discussion:** Internally structured by first presenting observational data or fit graphs, followed by the explicit mathematical calculation of the final value[cite: 5, 6, 7]. The discussion portion consistently features a numbered list detailing specific sources of systematic error[cite: 5, 6, 7].
*   **Conclusion:** Consistently 1 paragraph[cite: 5, 6]. Restates the exact final numerical result, compares it to the accepted value, and summarises the systematic errors[cite: 5, 6, 7].
*   **Acknowledgment:** Consistently 1-2 sentences strictly reserved for declaring the use of AI tools for formatting and plotting[cite: 5, 6, 7].

## SECTION 3: LANGUAGE AND TONE
*   **Voice and Pronoun Use:** The author uses a mixed voice. Passive voice is frequently used for general procedural descriptions ("The thickness of a soap bubble was determined..."[cite: 5], "Diffraction angles were measured..."[cite: 6]). However, the author frequently transitions to the first-person plural ("we") when describing specific physical actions, analytical decisions, or mathematical steps (e.g., "we balanced the pendulum"[cite: 7], "We avoided approximations"[cite: 6], "we can find our final experimental value"[cite: 5]). The first-person singular ("I") is entirely absent from the main text and appears only in the Acknowledgments[cite: 5, 6, 7].
*   **Formality and Tone:** The tone is highly formal, objective, and academic throughout the main text[cite: 5, 6, 7]. 
*   **Sentence Structure:** Sentences are often long and complex, linking a procedural action with its justification or outcome in a single sentence. *Example:* "To measure the period of the hanging pendulum, we clamped a rectangular piece of metal with a cutout for the pendulum to the table strongly, to ensure there was no movement that would introduce excess random error into our measurements, then balanced the pendulum of the metal piece such that the knife edge sat level."[cite: 7].
*   **Certainty and Hedging:** The author expresses absolute certainty regarding statistical data and measurements, but uses precise hedging language when attributing causes to errors. *Examples:* "...likely from fringe distortion..."[cite: 5], "...suggesting that most of our errors were systematic..."[cite: 7].

## SECTION 4: MATHEMATICAL AND TECHNICAL CONTENT PRESENTATION
*   **Equation Numbering:** Display equations are consistently centred and numbered with right-aligned parentheses, e.g., "(1)", "(2)"[cite: 5, 6, 7].
*   **Variable Definition:** Variables are defined in continuous prose immediately following the equation, almost always starting with the word "where". *Example:* "...where S is the fringe shift, t is the thickness, n is the refractive index..."[cite: 5].
*   **Derivations and Steps:** The author prefers to show the explicit, step-by-step substitution of numerical values into the equations within the Results section. *Example:* "$I_R = \frac{1}{12}(0.27208)(0.792)^2 = 0.0142 kg m^2$"[cite: 7]. Error propagation derivations are explicitly written out as a sequence of fractional uncertainty equations[cite: 6, 7].
*   **Assumptions:** Physical assumptions are explicitly listed in the Theory section before calculations are applied. *Example:* "For our calculations, we will also assume a rigid body with no air resistance, and a frictionless pivot..."[cite: 7].
*   **Referencing Equations:** Equations are referred to in prose as "Eq. 1"[cite: 5], "Eq. (3)"[cite: 6], or simply by number in parentheses, "Substituting the measured values into (1), (2), and (3)"[cite: 7].

## SECTION 5: FIGURES, TABLES, AND GRAPHS
*   **Figure Captions:** Captions are placed below the figures and begin with "Fig." followed by the number[cite: 5, 6, 7]. Captions are highly descriptive, typically 2-3 sentences, explaining what the image shows and its analytical significance. *Example:* "Fig. 6. Residuals of the Rydberg fit. A zero-residual reference line is included. The residuals show no systematic trend and all fall within their uncertainties, confirming the model's validity."[cite: 6].
*   **Table Formats:** Tables are labelled above the table using Roman numerals and all-caps titles (e.g., "TABLE I SUMMARY OF MEASURED BALMER WAVELENGTHS")[cite: 5, 6]. 
*   **Graphs:** Graphs consistently feature a grid background, explicit axis labels with units in parentheses (e.g., "Wavelength $\lambda$ (nm)"), and legends enclosed in a box[cite: 5, 6]. 
*   **Error Bars and Residuals:** Error bars are consistently included on scatter plots[cite: 5, 6]. The author has a strong tendency to include a dedicated residual plot immediately following a linear fit plot to justify the validity of the model[cite: 5, 6].

## SECTION 6: UNCERTAINTY AND ERROR ANALYSIS
*   **Notation:** Final results are consistently presented using parenthetical $\pm$ notation with the unit outside the bracket. *Example:* "$t = (3256 \pm 120)$ nm"[cite: 5], "$g = (7.88 \pm 0.05) m s^{-2}$"[cite: 7].
*   **Location of Analysis:** Deep uncertainty analysis is concentrated in the Results & Discussion sections[cite: 5, 6, 7]. 
*   **Methodology:** The author habitually calculates the percentage deviation from the accepted theoretical value and explicitly compares this percentage to the calculated statistical/random uncertainty percentage to prove that systematic errors dominate the experiment[cite: 5, 6, 7].
*   **Error Listing:** Systematic errors are always presented as a numbered list with bolded or distinct titles for each point. *Example:* "1) Wavelength: Uncertainty in our value...", "2) Refractive Index: The uncertainty..."[cite: 5].

## SECTION 7: REFERENCING AND CITATIONS
*   **Citation Format:** The author uses IEEE style. In-text citations appear as bracketed numbers at the end of sentences, before the period (e.g., "...accepted value of $9.81 m s^{-2}$ [1].")[cite: 5, 6, 7].
*   **Reference List:** Appears at the end of the document as a numbered list in brackets[cite: 5, 6, 7].
*   **Source Types:** Consistently cites university laboratory manuals, standard physics textbooks (e.g., Young & Freedman, Boas), and occasionally websites or standard databases (NIST)[cite: 5, 6, 7].
*   **Concentration:** Citations are heavily concentrated in the Introduction and Theory sections, with occasional citations in the Conclusion to reference the accepted theoretical values[cite: 5, 6, 7].

## SECTION 8: TRANSITIONS AND LOGICAL FLOW
*   **Signposting:** The author uses explicit, functional transitional phrases to move between mathematical steps. *Examples:* "Substituting the measured values into...", "The fractional uncertainty in $I_P$ is then...", "The uncertainty in g is then given by:"[cite: 7].
*   **Linking Theory to Results:** The discussion section heavily relies on backward referencing to the assumptions established in the Theory section. If an assumption (like small-angle approximation) is mentioned in Theory[cite: 7], its failure is discussed as a primary error source in the Discussion[cite: 7].

## SECTION 9: RECURRING PHRASES AND VOCABULARY
*   "The aim of this experiment was to..." (Appears in Abstracts and Introductions)[cite: 6, 7].
*   "...representing a [X]% deviation from the accepted value..." (Appears in Abstracts and Conclusions)[cite: 6, 7].
*   "This confirms that while the experimental technique was repeatable, several [systematic/uncorrected] errors affected the measured value..." (Appears in Conclusions)[cite: 6, 7].
*   "...indicating that systematic effects dominate..." (Appears across all reports when comparing statistical uncertainty to actual deviation)[cite: 5, 6, 7].
*   "I used Chat GPT to help format my content for LaTeX..." (Appears verbatim or near-verbatim in every Acknowledgment)[cite: 5, 6, 7].

## SECTION 10: WHAT THE AUTHOR CONSISTENTLY AVOIDS OR OMITS
*   **First-Person Singular ("I"):** Entirely absent from the scientific prose (Abstract through Conclusion). The author strictly uses "we" or passive voice[cite: 5, 6, 7].
*   **Bullet Points:** The author never uses standard bullet points for lists in the main text; lists (especially of errors or procedural steps) are always numbered with a closing parenthesis, e.g., "1)", "2)", "3)"[cite: 5, 6, 7].
*   **Unsubstantiated Fits:** The author avoids presenting linear fits without concurrently discussing the residuals or the reduced chi-squared value to prove the fit's statistical validity[cite: 5, 6].

## SECTION 11: VARIATION BETWEEN REPORTS
*   **Merging of Results and Discussion:** Report 1[cite: 5] separates "V. RESULTS" and "VI. DISCUSSION". Reports 2 and 3[cite: 6, 7] combine them into a single section. This appears driven by the complexity of the data analysis: in Reports 2 and 3, the final values are derived through a lengthy sequence of calculations and error propagations that require immediate discursive justification, making separation impractical.
*   **Pronoun Usage:** Report 1 relies almost entirely on the passive voice in the Methods section ("The thickness... was determined", "The experimental setup consisted of...")[cite: 5]. Reports 2 and 3 introduce "we" much more frequently ("we re-measured", "we balanced")[cite: 6, 7]. This suggests an evolution in the author's stylistic preference toward active, first-person plural descriptions of manual laboratory actions.

## SECTION 12: SUMMARY STYLE PROFILE
To accurately replicate this author's writing style in a lab report, adhere strictly to the following directives:

1.  **Structure:** Use a two-column IEEE format with capitalised, Roman-numeral headings. Order the sections: Abstract, Introduction, Theory, Methods, Results & Discussion (combined), Conclusion, Acknowledgments, References.
2.  **Voice:** Use passive voice for generic procedural statements, but actively use the first-person plural ("we") when describing specific analytical choices, mathematical substitutions, or physical actions taken during the experiment. Never use "I" outside of the Acknowledgments.
3.  **Abstract and Conclusion Formulas:** Open the Abstract with "The aim of this experiment was to...". In both the Abstract and Conclusion, explicitly state the final result in $(Value \pm Error)$ [Unit] format, explicitly state the percentage deviation from the accepted value, and explicitly compare this to the statistical uncertainty to conclude that systematic errors dominate.
4.  **Math Presentation:** Centre and number all display equations with right-aligned parentheses. Immediately following the equation, define all variables in a continuous prose sentence beginning with "where".
5.  **Calculations:** Show the explicit substitution of numbers into formulas in the Results section. Write out the step-by-step fractional uncertainty propagation derivations algebraically before substituting numbers.
6.  **Error Listing:** When discussing systematic errors in the Discussion section, format them exclusively as a numbered list using the format "1) **Bold/Clear Title:** Explanation...". Never use bullet points.
7.  **Data Validation:** Whenever a linear fit is used, you must explicitly mention the reduced chi-squared value or reference a residual plot to justify the validity of the linear model.
8.  **Signposting:** Use explicit transitional phrases like "Substituting the measured values into (1)..." and "The uncertainty in [X] is then given by:" to connect mathematical steps.
9.  **Acknowledgments:** Include a single sentence under an "ACKNOWLEDGMENT" heading stating: "I used ChatGPT to help format my content for LaTeX."
10. **Citations:** Use IEEE bracketed citations (e.g., [1]) heavily in the Introduction and Theory sections, and include a numbered reference list at the end.