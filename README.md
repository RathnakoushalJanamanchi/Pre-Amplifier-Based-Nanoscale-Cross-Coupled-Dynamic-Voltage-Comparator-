# Pre-Amplifier Based Nanoscale Cross Coupled Dynamic Voltage Comparator for Future Analog to Digital Converters (ADCs): A Reliability Study

> **Published at:** 16th ICCCNT IEEE Conference, July 6–11, 2025, IIT Indore, Madhya Pradesh, India  
> **IEEE Paper ID:** 64833  
> **©2025 IEEE**

---

## Authors

| Name | Affiliation | Contact |
|------|-------------|---------|
| Bhashaveni Ajay | School of Engineering/ECE, SR University, Warangal, India | bhashaveniajayyadav@gmail.com |
| J. Ajayan | School of Engineering/ECE, SR University, Warangal, India | email2ajayan@gmail.com |
| J. Rathna Koushal | School of Engineering/ECE, SR University, Warangal, India | koushaljanamanchi2525@gmail.com |

---

## Abstract

This work presents a high-speed, low-power **Dynamic Voltage Comparator (DVC)** featuring a **cross-coupled (CC) pair** in the pre-amplifier stage combined with a **Strong-Arm latch**, implemented in **16-nm CMOS technology**.

The proposed cross-coupled modification enhances both common-mode (CM) and differential-mode gains of the pre-amplifier, improving latch input voltages and enabling:
- **22% faster regeneration** over the standard comparator at low input differential voltages
- **21% lower Energy-Delay Product (EDP)** compared to existing literature
- **Immunity of delay to common-mode voltage variations**

---

## Key Performance Summary

| Condition | Delay | Power |
|-----------|-------|-------|
| VDD = 0.7 V, T = 300 K, ΔVin = 0.1 V | < 61.89 pS | 4.529 µW |
| VDD = 1.1 V, T = 300 K, ΔVin = 0.1 V | 27.26 pS | 53.06 µW |
| VDD = 0.7 V, T = 380 K, ΔVin = 0.1 V | 94.64 pS | 4.137 µW |
| VDD = 0.7 V, T = 300 K, ΔVin = 0.6 V | 39.34 pS | 4.807 µW |
| VDD = 0.7 V, T = 380 K, ΔVin = 0.6 V | 52.32 pS | 4.327 µW |

---

## Circuit Architecture

### Operating Phases

| Phase | CLK State | Action |
|-------|-----------|--------|
| Reset | CLK = 0 | M18, M19 reset pre-amplifier output to GND; M2–M6 reset latch output and intermediate nodes to VDD; M16, M17 (CC pair) turned OFF via tail M15 |
| Comparison | CLK = VDD | Tail transistors M12, M15 activated; M13, M14 (input) and M16, M17 (CC pair) turn ON; parasitic capacitors at Vp, Vn begin charging; CC pair boosts differential and CM gain |

### Design Specifications

| Parameter | Value |
|-----------|-------|
| Technology node | 16-nm CMOS |
| Total transistors | 21 |
| Pre-amplifier modification | PMOS cross-coupled pair (M16, M17) + third tail (M15) |
| Latch type | Strong-Arm |
| Supply voltage range tested | 0.7 V – 1.1 V |
| Temperature range tested | 300 K – 380 K |
| Input differential voltage (ΔVin) range | 0.1 V – 0.6 V |
| Simulation tool | SPICE |

### Key Improvement Mechanism

When Vinp > Vinn:
- Vsg of M13 < Vsg of M14 → Vp charges faster than Vn
- Faster Vp charging → higher Vsg of M16 vs. M17
- CC pair accelerates Vp node charging further
- Net effect: boosted differential signal gain + increased latch CM input voltage → improved latch speed

---

## Simulation Results

### A. ΔVin = 0.1 V

#### Delay (pS) vs. VDD at different temperatures
| VDD (V) | 300 K | 380 K |
|---------|-------|-------|
| 0.7 | 61.89 | 91.64 |
| 1.1 | 27.26 | 32.69|
#### Power (µW) vs. VDD at different temperatures

| VDD (V) | 300 K | 380 K |
|---------|-------|-------|
| 0.7 | 4.529 | 4.137 |
| 1.1 | 53.06 | 41.58 |

> Lower differential voltage (ΔVin = 0.1V) results in the highest delay. Increasing VDD from 0.7V to 1.1V reduces delay by ~56% at 300K.

---

### B. ΔVin = 0.2 V

#### Delay (pS)

| VDD (V) | 300 K | 380 K |
|---------|-------|-------|
| 0.7 | 50.78 | 75.19 |
| 1.1 | 25.69 | 30.66 |

#### Power (µW)

| VDD (V) | 300 K | 380 K |
|---------|-------|-------|
| 0.7 | 4.625 | 4.181 |
| 1.1 | 51.97 | 41.92 |

---

### C. ΔVin = 0.3 V

#### Delay (pS)

| VDD (V) | 300 K | 380 K |
|---------|-------|-------|
| 0.7 | 53.78 | 74.04 |
| 1.1 | 24.79 | 29.69 |

#### Power (µW)

| VDD (V) | 300 K | 380 K |
|---------|-------|-------|
| 0.7 | 4.878 | 4.253 |
| 1.1 | 54.02 | 42.53 |

> The DVC exhibits excellent reliability at high temperatures for both power and speed metrics at ΔVin = 0.3V.

---

### D. ΔVin = 0.4 V

#### Delay (pS)

| VDD (V) | 300 K | 380 K |
|---------|-------|-------|
| 0.7 | 44.56 | 60.64 |
| 1.1 | 24.32 | 29.07 |

#### Power (µW)

| VDD (V) | 300 K | 380 K |
|---------|-------|-------|
| 0.7 | 4.895 | 4.281 |
| 1.1 | 54.56 | 42.67 |

---

### E. ΔVin = 0.5 V

#### Delay (pS)

| VDD (V) | 300 K | 380 K |
|---------|-------|-------|
| 0.7 | 40.92 | 55.23 |
| 1.1 | 26.76 | 32.49 |

#### Power (µW)

| VDD (V) | 300 K | 380 K |
|---------|-------|-------|
| 0.7 | 4.779 | 4.297 |
| 1.1 | 52.00 | 42.09 |

---

### F. ΔVin = 0.6 V

#### Delay (pS)

| VDD (V) | 300 K | 380 K |
|---------|-------|-------|
| 0.7 | 39.34 | 52.32 |
| 1.1 | 25.23 | 30.50 |

#### Power (µW)

| VDD (V) | 300 K | 380 K |
|---------|-------|-------|
| 0.7 | 4.807 | 4.327 |
| 1.1 | 53.50 | 41.75 |

> At ΔVin = 0.6V, delay is lowest across all ΔVin conditions, confirming faster regeneration at higher differential inputs.

---

### G. Summary: Delay vs. ΔVin at 300 K

| ΔVin (V) | Delay @ 0.7V VDD (pS) | Delay @ 1.1V VDD (pS) | Reduction (%) |
|----------|----------------------|----------------------|---------------|
| 0.1 | 61.89 | 27.26 | ~56% |
| 0.2 | 50.78 | 25.69 | ~49% |
| 0.3 | 53.78 | 24.79 | ~54% |
| 0.4 | 44.56 | 24.32 | ~45% |
| 0.5 | 40.92 | 26.76 | ~35% |
| 0.6 | 39.34 | 25.23 | ~36% |

### H. Summary: Power vs. ΔVin at 300 K

| ΔVin (V) | Power @ 0.7V VDD (µW) | Power @ 1.1V VDD (µW) |
|----------|----------------------|----------------------|
| 0.1 | 4.529 | 53.06 |
| 0.2 | 4.625 | 51.97 |
| 0.3 | 4.878 | 54.02 |
| 0.4 | 4.895 | 54.56 |
| 0.5 | 4.779 | 52.00 |
| 0.6 | 4.807 | 53.50 |

### I. Temperature Effects: Delay vs. Temperature at 0.7V VDD

| ΔVin (V) | Delay @ 300 K (pS) | Delay @ 380 K (pS) | Increase (%) |
|----------|--------------------|--------------------|--------------|
| 0.1 | 61.89 | 94.64 | ~53% |
| 0.6 | 39.34 | 52.32 | ~33% |

### J. Temperature Effects: Power vs. Temperature at 0.7V VDD

| ΔVin (V) | Power @ 300 K (µW) | Power @ 380 K (µW) | Change |
|----------|--------------------|--------------------|--------|
| 0.1 | 4.529 | 4.137 | −8.7% |
| 0.6 | 4.807 | 4.327 | −10.0% |

> Power consumption at low VDD slightly decreases with rising temperature — beneficial for thermally stressed environments.

---

## Figures

> Place simulation output images in the `figures/` directory and they will render below.

| Figure | Description | File |
|--------|-------------|------|
| Fig. 1 | Circuit diagram of the cross-coupled comparator | `figures/fig1_circuit_diagram.png` |
| Fig. 2 | Power and delay at ΔVin = 0.1V | `figures/fig2_dvin_0.1V.png` |
| Fig. 3 | Power and delay at ΔVin = 0.2V | `figures/fig3_dvin_0.2V.png` |
| Fig. 4 | Power and delay at ΔVin = 0.3V | `figures/fig4_dvin_0.3V.png` |
| Fig. 5 | Power and delay at ΔVin = 0.4V | `figures/fig5_dvin_0.4V.png` |
| Fig. 6 | Power and delay at ΔVin = 0.5V | `figures/fig6_dvin_0.5V.png` |
| Fig. 7 | Power and delay at ΔVin = 0.6V | `figures/fig7_dvin_0.6V.png` |
| Fig. 8 | Delay and power vs. temperature at different VDD and ΔVin | `figures/fig8_temperature_effects.png` |

To display figures inline, add them like this after uploading to your repo:

```markdown
![Circuit Diagram](figures/fig1_circuit_diagram.png)
![ΔVin = 0.1V](figures/fig2_dvin_0.1V.png)
```

---

## Comparison with Prior Art

| Work | Delay | EDP | Technology |
|------|-------|-----|------------|
| Sharma et al. [11] (baseline) | < 160 pS | 81 fJ·ns | — |
| **This Work** | **< 61.89 pS** | **21% lower than [11]** | **16-nm CMOS** |

> This DVC achieves **22% faster regeneration** and **21% lower EDP** compared to the reference design.

---

## Conclusion

This work demonstrates a comprehensive reliability study of a cross-coupled dynamic voltage comparator in 16-nm CMOS technology. Key findings:

- The **cross-coupled pre-amplifier** boosts both differential-mode and common-mode gain, reducing pre-amplifier delay and latch regeneration time simultaneously.
- **Delay is immune to common-mode voltage variations**, a critical advantage for ADC applications.
- At low supply (0.7V), the DVC maintains very low power (~4.5 µW), suitable for IoT and battery-constrained systems.
- At high supply (1.1V), the DVC achieves sub-30 pS delay, suitable for high-speed ADC front-ends.
- Reliability is maintained across a wide temperature range (300K–380K) with well-behaved power and delay trends.

**Future scope:** This DVC can be further enhanced using emerging device technologies such as graphene FETs, CNTFETs, nanosheet (NS)-FETs, or Forksheet (FS)-FETs.
---

## Citation

```bibtex
@inproceedings{ajay2025dvc,
  title     = {Pre-Amplifier Based Nanoscale Cross Coupled Dynamic Voltage Comparator 
               for Future Analog to Digital Converters (ADCs): A Reliability Study},
  author    = {Bhashaveni Ajay and J. Ajayan and J. Rathna Koushal},
  booktitle = {16th International Conference on Computing, Communication and Networking 
               Technologies (ICCCNT)},
  year      = {2025},
  month     = {July},
  address   = {IIT Indore, Madhya Pradesh, India},
  note      = {IEEE Paper ID: 64833},
  publisher = {IEEE}
}
```

---

## References

1. L. Kull et al., "A 24–72-GS/s 8-b Time-Interleaved SAR ADC With 2.0–3.3-pJ/Conversion and >30 dB SNDR at Nyquist in 14-nm CMOS FinFET," *IEEE JSSC*, vol. 53, no. 12, pp. 3508–3516, Dec. 2018.
2. A. T. Ramkaj et al., "A 28 nm CMOS Triple-Latch Feed-Forward Dynamic Comparator With <27 ps / 1 V and <70 ps / 0.6 V Delay at 5 mV-Sensitivity," *IEEE TCAS-I*, vol. 69, no. 11, pp. 4404–4414, Nov. 2022.
3. D. Dermit et al., "A 1.67-GSps TI 10-Bit Ping-Pong SAR ADC With 51-dB SNDR in 16-nm FinFET," *IEEE SSCL*, vol. 3, pp. 150–153, 2020.
4. S.-B. Yu et al., "Pulsed-Laser-Induced Single-Event Upset in Dynamic Comparator by Incorporating Experimental Parameters Into Simulations," *IEEE TIM*, vol. 73, Art no. 2007312, 2024.
5. S. Babayan-Mashhadi and R. Lotfi, "Analysis and Design of a Low-Voltage Low-Power Double-Tail Comparator," *IEEE TVLSI*, vol. 22, no. 2, pp. 343–352, Feb. 2014.
6. H. S. Bindra et al., "A 1.2-V Dynamic Bias Latch-Type Comparator in 65-nm CMOS With 0.4-mV Input Noise," *IEEE JSSC*, vol. 53, no. 7, pp. 1902–1912, July 2018.
7. J. Lee et al., "A 0.56-mW 63.6-dB SNDR 250-MS/s Two-Step SAR ADC in 8-nm FinFET," *IEEE SSCL*, vol. 5, pp. 256–259, 2022.
8. H. Xu and A. A. Abidi, "Analysis and Design of Regenerative Comparators for Low Offset and Noise," *IEEE TCAS-I*, vol. 66, no. 8, pp. 2817–2830, Aug. 2019.
9. S. Chevella, D. O'Hare, and I. O'Connell, "A Low-Power 1-V Supply Dynamic Comparator," *IEEE SSCL*, vol. 3, pp. 154–157, 2020.
10. K. Krishna and N. Nambath, "Cascode Cross-Coupled Stage High-Speed Dynamic Comparator in 65 nm CMOS," *IEEE TVLSI*, vol. 31, no. 7, pp. 1083–1086, July 2023.
11. N. Sharma, V. Hande, and D. M. Das, "A Dynamic Comparator With Cross-Coupled Pre-Amplifier With <160 ps Delay and 81 fJ·ns EDP," *Integrated Circuits and Systems*, vol. 1, no. 4, pp. 206–213, Sept.–Oct. 2024.

---

## License

© 2025 IEEE. Personal use of this material is permitted. For any other use, permission must be obtained from IEEE.
