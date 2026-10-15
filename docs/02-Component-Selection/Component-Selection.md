---

---
title: Component Selection
---

# Component Selection

## User Controls & Safety Subsystem

The User Controls & Safety subsystem provides the user interface for controlling the operation of the robotic system. This subsystem includes an emergency stop button, a start/pause button, a speed control input, status indicator LEDs, and an audible warning device.

The following component selections are based on the subsystem block diagram, electrical compatibility with the PIC18F57Q43 microcontroller, cost, PCB integration, and overall system requirements.

---

## 1. Speed Control Input Selection

The speed control input allows the operator to adjust the operating speed of the robotic system.

According to the current block diagram, the speed control device connects to the RA0/ANA0 analog input of the PIC18F57Q43 microcontroller.

Three potential solutions were evaluated.

*Table 1: Speed Control Input Component Selection*

**Speed Control Input**

| **Solution** | **Pros** | **Cons** |
| --- | --- | --- |
| ![Rotary Potentiometer](images/speed_rotary.png)<br>**Option 1.**<br>Bourns PTV09A-4015F-B103<br>10k Ohm Linear Rotary Potentiometer<br>**$0.89/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/bourns-inc/PTV09A-4015F-B103/3781113)<br>[Datasheet](https://www.bourns.com/docs/product-datasheets/PTV09.pdf) | • Provides a continuous analog voltage directly compatible with the PIC ADC input.<br>• Inexpensive compared with the other options.<br>• Compact design suitable for a user control panel.<br>• Through-hole mounting simplifies PCB assembly. | • Mechanical contact wear can introduce electrical noise over time.<br>• Limited to approximately 280 degrees of rotation.<br>• May require software filtering or calibration for stable speed adjustment. |
| ![Slide Potentiometer](images/speed_slide.png)<br>**Option 2.**<br>Bourns PTA2043-2010DPB103<br>10k Ohm Linear Slide Potentiometer<br>**$1.43/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/bourns-inc/PTA2043-2010DPB103/3781175)<br>[Datasheet](https://www.bourns.com/docs/Product-Datasheets/pta.pdf) | • Provides a continuous analog voltage compatible with the PIC ADC input.<br>• The slider position allows users to visually estimate the selected speed.<br>• Linear resistance characteristics simplify the interpretation of speed settings.<br>• Supports through-hole PCB mounting. | • Requires more physical space than a rotary potentiometer.<br>• More expensive than Option 1.<br>• Sliding contacts may be affected by dust and mechanical wear.<br>• Requires a different panel layout from the current speed knob design. |
| ![Rotary Encoder](images/speed_encoder.png)<br>**Option 3.**<br>Bourns PEC11R-4215K-N0024<br>24 PPR Incremental Rotary Encoder<br>**$2.83/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/bourns-inc/PEC11R-4215K-N0024/4699218)<br>[Datasheet](https://www.bourns.com/docs/product-datasheets/pec11r.pdf) | • Supports continuous rotation without fixed mechanical end stops.<br>• Digital signals allow adjustable speed increments through software.<br>• Suitable for applications requiring step-by-step adjustment.<br>• Through-hole mounting is available for PCB integration. | • Requires two digital input channels instead of the existing analog input.<br>• Requires additional software for quadrature decoding and debouncing.<br>• More expensive than the other two solutions.<br>• Would require modifications to the current block diagram and microcontroller pin assignments. |

**Choice:** Option 1: Bourns PTV09A-4015F-B103 Linear Rotary Potentiometer.

**Rationale:** The Bourns PTV09A-4015F-B103 rotary potentiometer was selected because it provides a simple and reliable method for controlling the operating speed of the robotic system.

The selected component has a 10k Ohm resistance and a linear taper, allowing the microcontroller to interpret the potentiometer position through its analog-to-digital converter. This is compatible with the current subsystem block diagram, which assigns the speed control input to RA0/ANA0.

Compared with the slide potentiometer, the rotary potentiometer requires less panel space and provides an intuitive knob-based control interface. Compared with the rotary encoder, it requires fewer microcontroller input pins and does not need additional quadrature decoding software.

Furthermore, its through-hole mounting simplifies PCB integration, while its relatively low unit cost makes it suitable for the initial prototype.

Therefore, Option 1 provides the best balance of electrical compatibility, design simplicity, cost, and ease of integration for the User Controls & Safety subsystem.



---

## 2. Buzzer / Audio Alert Selection

The Buzzer / Audio Alert component is responsible for providing audible warnings when the robotic system encounters an emergency stop condition or an operating fault.

According to the subsystem block diagram, the buzzer is controlled by the PIC18F57Q43 microcontroller through the RB4 PWM output.

The selected buzzer should operate with the system's 5V power supply, provide sufficient sound output for laboratory use, and support programmable warning patterns.

Three potential solutions were evaluated.

*Table 2: Buzzer / Audio Alert Component Selection*

**Buzzer / Audio Alert**

| **Solution** | **Pros** | **Cons** |
| --- | --- | --- |
| ![Passive Piezo Buzzer](images/buzzer_piezo.png)<br>**Option 1.**<br>Same Sky CPT-1407-5TH<br>Passive Piezoelectric Buzzer<br>5V, 5mA, 4kHz, 85dB<br>**$0.62/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/CPT-1407-5TH/29292280) | • Compatible with externally generated PWM signals.<br>• Low nominal current consumption of 5mA.<br>• Inexpensive compared with the other options.<br>• Through-hole mounting simplifies PCB assembly.<br>• Supports programmable warning tones and alert patterns. | • Requires an external oscillating signal to generate sound.<br>• May require additional driver circuitry for reliable operation.<br>• Sound output depends on the selected drive frequency and waveform.<br>• Requires additional PWM configuration in software. |
| ![Active Piezo Buzzer](images/buzzer_active.png)<br>**Option 2.**<br>Same Sky CPI-137-83T<br>Active Piezoelectric Buzzer<br>5V, 10mA, 3.8kHz, 83dB<br>**$2.69/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/CPI-137-83T/11480414) | • Contains an internal oscillator and does not require an external audio-frequency PWM signal.<br>• Simple on/off control for warning applications.<br>• Operates from the 5V power supply.<br>• Through-hole mounting is suitable for PCB integration. | • Higher cost than the passive piezoelectric buzzer.<br>• Higher nominal current consumption than Option 1.<br>• Fixed internal operating frequency limits tone customization.<br>• Cannot directly use PWM frequency adjustment to generate different audio tones. |
| ![Magnetic Buzzer](images/buzzer_magnetic.png)<br>**Option 3.**<br>Same Sky CEM-1206S<br>Passive Magnetic Buzzer<br>5V, 45mA, 2.4kHz, 85dB<br>**$1.19/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/CEM-1206S/412414) | • Supports externally generated audio-frequency signals.<br>• Provides audible sound output suitable for warning applications.<br>• Compact 12mm through-hole design.<br>• Lower component cost than Option 2. | • Higher nominal current consumption of 45mA.<br>• Requires an external driver because of its current requirements.<br>• Magnetic construction introduces inductive switching considerations.<br>• Requires additional protection circuitry when driven by a switching transistor. |

**Choice:** Option 1: Same Sky CPT-1407-5TH Passive Piezoelectric Buzzer.

**Rationale:** The CPT-1407-5TH passive piezoelectric buzzer was selected because it offers a suitable combination of PWM compatibility, low power consumption, compact size, and affordable cost for the User Controls & Safety subsystem.

The selected buzzer operates at a nominal voltage of 5V and has a specified operating frequency of 4kHz, making it suitable for use with a PWM signal generated by the PIC18F57Q43 microcontroller.

Compared with the active piezoelectric buzzer, Option 1 provides greater flexibility in generating different warning patterns and tones. Unlike the active buzzer, which contains its own oscillator, the passive buzzer allows the microcontroller to determine the frequency and timing of the warning signal.

Compared with the magnetic buzzer, Option 1 has significantly lower nominal current consumption, reducing the load on the subsystem's power supply.

Furthermore, its through-hole package simplifies PCB assembly and its 14mm diameter is suitable for integration into the user control board.

A suitable driver circuit will be evaluated during schematic design to ensure that the buzzer is driven within its electrical specifications.

Therefore, Option 1 provides the best overall balance of electrical compatibility, current consumption, cost, and controllability for the robotic system's audible warning function.


---

## 3. Buzzer Driver / Switching Device Selection

The buzzer driver is responsible for switching the audible warning device using a PWM control signal from the PIC18F57Q43 microcontroller.

The selected buzzer, Same Sky CPT-1407-5TH, is an externally driven piezoelectric transducer with a nominal current consumption of 5mA at its specified test conditions.

The driver should support the 5V buzzer supply, interface with the microcontroller's RB4 PWM signal, and be suitable for integration into the subsystem PCB.

Three switching devices were evaluated.

*Table 3: Buzzer Driver / Switching Device Selection*

**Buzzer Driver / Switching Device**

| **Solution** | **Pros** | **Cons** |
| --- | --- | --- |
| ![NPN Transistor](images/driver_2n3904.png)<br>**Option 1.**<br>onsemi 2N3904TF<br>NPN Bipolar Junction Transistor<br>40V, 200mA, TO-92<br>**$0.29/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/onsemi/2N3904TF/975251)<br>[Datasheet](https://www.onsemi.com/pdf/datasheet/2n3904-d.pdf) | • Supports low-current switching applications.<br>• Can be controlled using a 3.3V or 5V GPIO signal with an appropriate base resistor.<br>• Through-hole TO-92 package simplifies PCB assembly and soldering.<br>• Low component cost.<br>• Easily interfaces with the existing PWM control signal. | • Requires a base current during operation.<br>• Requires an additional base resistor.<br>• Has a collector-emitter saturation voltage when switched on.<br>• Not as power-efficient as a suitable MOSFET for higher-current applications. |
| ![N-Channel MOSFET](images/driver_2n7000.png)<br>**Option 2.**<br>Diotec Semiconductor 2N7000<br>N-Channel MOSFET<br>60V, 200mA, TO-92<br>**$0.29/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/diotec-semiconductor/2N7000/13164314)<br>[Datasheet](https://diotec.com/request/datasheet/2n7000.pdf) | • Voltage-controlled gate requires very little steady-state current.<br>• Through-hole mounting simplifies manual PCB assembly.<br>• Suitable for low-current switching applications.<br>• Low cost compared with other driver solutions. | • Low on-resistance is specified at higher gate-drive voltages, not guaranteed at 3.3V.<br>• Switching performance must be verified with the actual GPIO voltage.<br>• Requires a gate pull-down resistor for reliable startup behavior.<br>• Provides no significant functional advantage over the NPN transistor for this low-current buzzer. |
| ![Logic-Level MOSFET](images/driver_ao3400.png)<br>**Option 3.**<br>Alpha & Omega AO3400A<br>Logic-Level N-Channel MOSFET<br>30V, 5.7A rated, SOT-23<br>**$0.52/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/alpha-omega-semiconductor-inc/AO3400A/1855942)<br>[Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/1133/AO3400A_ds.pdf) | • Low on-resistance, including at a 2.5V gate-drive voltage.<br>• Compatible with low-voltage microcontroller control signals.<br>• Requires very little steady-state gate current.<br>• Suitable for PWM switching applications.<br>• Compact PCB footprint. | • Small SOT-23 surface-mount package requires more careful soldering.<br>• Higher price than Options 1 and 2.<br>• Current capability is much greater than needed for the selected buzzer.<br>• Requires a gate pull-down resistor to prevent unintended switching during startup. |

**Choice:** Option 1: onsemi 2N3904TF NPN Bipolar Junction Transistor.

**Rationale:** The onsemi 2N3904TF NPN transistor was selected because it provides a simple, affordable, and practical switching solution for the User Controls & Safety subsystem.

The selected CPT-1407-5TH piezoelectric buzzer has a nominal operating current of approximately 5mA under its specified test conditions. The 2N3904TF transistor has a maximum collector current rating of 200mA, which provides adequate current-handling capability for the intended low-current application.

The transistor can be controlled using the PWM output from the PIC18F57Q43 through a properly sized base resistor. This allows the microcontroller to control the buzzer while using the subsystem's 5V power supply for the load.

Compared with the 2N7000 MOSFET, the 2N3904TF offers a straightforward interface without concerns about whether the available 3.3V GPIO signal will provide sufficiently low MOSFET on-resistance.

Compared with the AO3400A, the selected transistor is easier to assemble manually because it uses a through-hole TO-92 package instead of a small surface-mount package.

Although the 2N3904TF requires base current during operation, its low cost, simple switching circuit, and adequate current capability make it suitable for this application.

Therefore, Option 1 provides an appropriate balance of electrical compatibility, ease of assembly, cost, and circuit simplicity for the buzzer driver.

The final driver circuit and its output waveform will be verified during schematic development and hardware testing.


---

## 4. Power Source and Voltage Regulation Selection

The User Controls & Safety subsystem requires a stable 5V power supply to operate the PIC18F57Q43 microcontroller and its peripheral components.

According to the EGR304 project requirements, each individual subsystem must include a 5V linear voltage regulator and a barrel jack connection for a 9V external power supply.

The power system must provide stable voltage regulation, sufficient current capacity, and safe operating conditions for all connected components.

### 4.1 Linear Voltage Regulator Selection

Three 5V linear voltage regulators were evaluated based on electrical characteristics, current capacity, cost, and PCB integration.

*Table 4: Linear Voltage Regulator Selection*

**5V Linear Voltage Regulator**

| **Solution** | **Pros** | **Cons** |
| --- | --- | --- |
| ![L7805CV](images/regulator_l7805.png)<br>**Option 1.**<br>STMicroelectronics L7805CV<br>5V Fixed Linear Regulator<br>1.5A, TO-220<br>**$1.08/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964)<br>[Datasheet](https://www.st.com/resource/en/datasheet/l78.pdf) | • Provides a regulated 5V output compatible with the subsystem.<br>• Supports a 9V DC input supply.<br>• Rated for up to 1.5A with appropriate thermal management.<br>• Inexpensive compared with the other options.<br>• Through-hole TO-220 package simplifies PCB assembly.<br>• Includes thermal shutdown and short-circuit protection. | • Generates heat because the excess input voltage is dissipated as power loss.<br>• May require a heatsink at higher load currents.<br>• Requires appropriate input and output capacitors.<br>• Higher dropout voltage compared with an LDO regulator. |
| ![L78M05CV](images/regulator_l78m05.png)<br>**Option 2.**<br>STMicroelectronics L78M05CV<br>5V Fixed Linear Regulator<br>500mA, TO-220<br>**$1.16/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/stmicroelectronics/L78M05CV/634721)<br>[Datasheet](https://www.st.com/resource/en/datasheet/l78m.pdf) | • Provides a regulated 5V output compatible with the subsystem.<br>• Supports a 9V input supply.<br>• Suitable for low-current electronic systems.<br>• Through-hole mounting simplifies PCB integration.<br>• Includes internal protection against overheating and short circuits. | • Lower rated current capacity of 500mA.<br>• Provides less current headroom for additional peripheral devices.<br>• Still dissipates excess voltage as heat.<br>• Slightly higher unit cost than Option 1. |
| ![L4940V5](images/regulator_l4940.png)<br>**Option 3.**<br>STMicroelectronics L4940V5<br>5V Low-Dropout Linear Regulator<br>1.5A, TO-220<br>**$2.68/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/stmicroelectronics/L4940V5/585925)<br>[Datasheet](https://www.st.com/resource/en/datasheet/l4940.pdf) | • Provides a stable regulated 5V output.<br>• Low dropout voltage supports operation with input voltages closer to 5V.<br>• Rated for up to 1.5A with adequate thermal management.<br>• Through-hole TO-220 package is suitable for PCB assembly.<br>• Includes thermal and short-circuit protection. | • More expensive than the other two solutions.<br>• Low-dropout capability offers limited benefit with the specified 9V supply.<br>• Still requires thermal management when reducing 9V to 5V.<br>• Requires appropriate input and output capacitors, including attention to output capacitor stability requirements. |

**Choice:** Option 1: STMicroelectronics L7805CV Linear Voltage Regulator.

**Rationale:** The STMicroelectronics L7805CV was selected because it provides a cost-effective and straightforward method for converting the required 9V input supply into a regulated 5V output.

The selected regulator supports a fixed 5V output and has a rated current capacity of up to 1.5A, subject to appropriate thermal management. This provides useful current capacity for the PIC18F57Q43 microcontroller and the subsystem's peripheral devices.

Compared with the L78M05CV, the L7805CV provides a higher rated output current at a slightly lower unit cost.

Compared with the L4940V5, the L7805CV offers a simpler and less expensive solution for the required 9V input. Since the subsystem uses a nominal 9V supply, the lower dropout voltage of the L4940V5 is not a significant advantage.

The TO-220 through-hole package also simplifies manual soldering, PCB integration, and possible heatsink installation.

Although linear regulation produces heat, the selected regulator is suitable for the proposed design provided that the final power budget and thermal calculations confirm safe operating conditions.

Therefore, Option 1 provides an appropriate balance of electrical compatibility, current capacity, cost, and PCB assembly requirements.

### 4.2 External 9V Power Source Selection

The external power source must supply 9V DC to the subsystem through a barrel jack connector.

Three commercially available AC/DC power adapters were evaluated based on voltage regulation, maximum current, connector compatibility, and cost.

*Table 5: External Power Source Selection*

**9V External Power Supply**

| **Solution** | **Pros** | **Cons** |
| --- | --- | --- |
| ![Jameco Power Adapter](images/power_jameco.png)<br>**Option 1.**<br>Jameco ReliaPro DCU090050RZ7480<br>9V DC Wall Adapter<br>500mA, 4.5W<br>**$10.53/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/jameco-reliapro/DCU090050RZ7480/25966183) | • Provides the required 9V DC output.<br>• Uses a center-positive 5.5mm/2.1mm barrel connector.<br>• Suitable for low-current subsystem applications.<br>• Compact wall-mounted power source. | • Limited to a maximum output current of 500mA.<br>• Provides less current headroom than the other options.<br>• Designed for 120V AC input rather than universal AC input.<br>• Requires verification that the final power budget fits within its current rating. |
| ![Pololu Power Adapter](images/power_pololu.png)<br>**Option 2.**<br>Pololu 1470<br>9V DC Wall Adapter<br>1A, 9W<br>**$11.41/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/pololu/1470/19200211) | • Provides the required 9V DC output.<br>• Supports a maximum output current of 1A.<br>• Compatible with 100–240V AC input.<br>• Uses a center-positive 5.5mm/2.1mm barrel connector.<br>• Provides sufficient current headroom for a moderate-load subsystem. | • Higher unit cost than the other two options.<br>• Lower current capacity than Option 3.<br>• Requires an external AC outlet.<br>• Connector fit and final load requirements must still be verified. |
| ![Tensility Power Adapter](images/power_tensility.png)<br>**Option 3.**<br>Tensility International 16-00134<br>9V DC Wall Adapter<br>2A, 18W<br>**$10.53/each**<br>[Link to Product](https://www.digikey.com/en/products/detail/tensility-international-corp/16-00134/10324425) | • Provides the required regulated 9V DC output.<br>• Supports a maximum output current of 2A.<br>• Compatible with 100–240V AC input.<br>• Uses a center-positive 5.5mm/2.1mm barrel connector.<br>• Provides additional source current headroom for future design changes. | • Higher current capacity than the present subsystem may require.<br>• Requires an external AC outlet and reduces portability.<br>• Must be connected to a barrel jack with matching dimensions and polarity.<br>• Additional adapter current capacity does not eliminate the linear regulator's thermal limitations. |

**Choice:** Option 3: Tensility International 16-00134 9V DC Wall Adapter.

**Rationale:** The Tensility International 16-00134 was provisionally selected because it provides the required 9V DC output with sufficient current capacity for the proposed power distribution system.

The adapter supports up to 2A of output current and operates from a 100–240V AC input. Its center-positive 5.5mm/2.1mm barrel connector is suitable for integration with a compatible PCB-mounted barrel jack.

Compared with the Jameco 500mA adapter, Option 3 provides greater current headroom for possible future changes to the subsystem.

Compared with the Pololu 1A adapter, Option 3 offers a higher rated current capacity at a similar or lower unit cost.

The higher current rating does not mean that the subsystem will continuously draw 2A. Actual current consumption depends on the connected components, while the linear regulator's safe output current will also depend on thermal conditions.

Therefore, Option 3 provides a practical external power source for the subsystem. The final selection will be confirmed after completing the power budget, verifying the barrel jack dimensions, and calculating regulator power dissipation.
