---
title: Bill of Materials
---

# User Controls & Safety — Bill of Materials (Rev C)

The list follows the **43 non-power symbols in the RevC KiCad schematic** and the selected external 9 V adapter. Historical selections are kept and otherwise unspecified components use **proposed, fully identified DigiKey catalogue choices**. The proposed models are not proof of an actual purchase; check physical dimensions and pinouts before ordering.

[Download editable BOM Excel](EGR304_BOM_RevC.xlsx) · [View KiCad RevC source](https://github.com/idtrfmnhcw/idtrfmnhcw_EGR304_F26.github.io/blob/main/docs/04-Schematic/EGR304_User_Controls_Project_RevC.zip)

## Part 1 — Bill of Materials (Table)

*Table 1. USD single-quantity catalogue reference prices as of 30 October 2026; shipping and taxes excluded.*

| Part Name / Description | Qty | Unit Cost (USD) | Total Cost (USD) | Manufacturer | Manufacturer # | Vendor Link | Datasheet / Specifications | Schematic Reference |
|:--|--:|--:|--:|:--|:--|:--|:--|:--|
| PIC18F57Q43 Curiosity Nano development board | 1 | $10.61 | $10.61 | Microchip | DM164150 | [DigiKey](https://www.digikey.com/en/products/detail/microchip-technology/DM164150/11586705) | [User guide](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F57Q43-Curiosity-Nano-HW-UserGuide-DS40002186B.pdf) | U1 |
| 5 V linear regulator, TO-220 | 1 | $1.08 | $1.08 | STMicroelectronics | L7805CV | [DigiKey](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964) | [ST L78](https://www.st.com/resource/en/datasheet/l78.pdf) | U2 |
| 7-channel Darlington driver, DIP-16 | 1 | $1.13 | $1.13 | Texas Instruments | ULN2003AN | [DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/ULN2003AN/277624) | [TI ULN2003A](https://www.ti.com/lit/ds/symlink/uln2003a.pdf) | U3 |
| Passive piezo buzzer, 4 kHz nominal | 1 | $0.62 | $0.62 | Same Sky | CPT-1407-5TH | [DigiKey](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/CPT-1407-5TH/29292280) | [Same Sky](https://www.sameskydevices.com/product/resource/cpt-1407-5th.pdf) | BZ1 |
| 10 kΩ linear rotary potentiometer | 1 | $0.89 | $0.89 | Bourns | PTV09A-4015F-B103 | [DigiKey](https://www.digikey.com/en/products/detail/bourns-inc/PTV09A-4015F-B103/3781113) | [Bourns PTV09](https://www.bourns.com/docs/product-datasheets/PTV09.pdf) | RV1 |
| Time-delay axial fuse, 315 mA, 250 V | 1 | $1.30 | $1.30 | SCHURTER | 0034.3112.PT | [DigiKey](https://www.digikey.com/en/products/detail/schurter-inc/0034-3112-PT/639954) | [Supplier specs](https://www.digikey.com/en/products/detail/schurter-inc/0034-3112-PT/639954) | F1 |
| 10 kΩ carbon-film resistor, ¼ W, ±5% | 4 | $0.10 | $0.40 | YAGEO | CFR-25JR-52-10K | [DigiKey](https://www.digikey.com/en/products/detail/yageo/CFR-25JR-52-10K/11998) | [Supplier specs](https://www.digikey.com/en/products/detail/yageo/CFR-25JR-52-10K/11998) | R1, R2, R9, R10 |
| 1 kΩ carbon-film resistor, ¼ W, ±5% | 4 | $0.10 | $0.40 | YAGEO | CFR-25JR-52-1K | [DigiKey](https://www.digikey.com/en/products/detail/yageo/CFR-25JR-52-1K/11974) | [Supplier specs](https://www.digikey.com/en/products/detail/yageo/CFR-25JR-52-1K/11974) | R3, R4, R5, R8 |
| 2.2 kΩ carbon-film resistor, ¼ W, ±5% | 1 | $0.11 | $0.11 | YAGEO | CFR-25JR-52-2K2 | [DigiKey](https://www.digikey.com/en/products/detail/yageo/CFR-25JR-52-2K2/11982) | [Supplier specs](https://www.digikey.com/en/products/detail/yageo/CFR-25JR-52-2K2/11982) | R6 |
| 100 kΩ carbon-film resistor, ¼ W, ±5% | 1 | $0.10 | $0.10 | YAGEO | CFR-25JR-52-100K | [DigiKey](https://www.digikey.com/en/products/detail/yageo/CFR-25JR-52-100K/18091927) | [Supplier specs](https://www.digikey.com/en/products/detail/yageo/CFR-25JR-52-100K/18091927) | R7 |
| 0.33 µF film capacitor, ≥25 V (63 V chosen) | 1 | $0.43 | $0.43 | KEMET | R82DC3330CK60J | [DigiKey](https://www.digikey.com/en/products/detail/kemet/R82DC3330CK60J/18302072) | [Supplier specs](https://www.digikey.com/en/products/detail/kemet/R82DC3330CK60J/18302072) | C1 |
| 0.1 µF film capacitor, ≥25 V (63 V chosen) | 2 | $0.28 | $0.56 | KEMET | R82DC3100AA50K | [DigiKey](https://www.digikey.com/en/products/detail/kemet/R82DC3100AA50K/3724647) | [Supplier specs](https://www.digikey.com/en/products/detail/kemet/R82DC3100AA50K/3724647) | C2, C5 |
| 0.1 µF film capacitor, 63 V | 1 | $0.28 | $0.28 | KEMET | R82DC3100AA50K | [DigiKey](https://www.digikey.com/en/products/detail/kemet/R82DC3100AA50K/3724647) | [Supplier specs](https://www.digikey.com/en/products/detail/kemet/R82DC3100AA50K/3724647) | C7 |
| 10 µF electrolytic capacitor, 25 V, polarized | 1 | $0.26 | $0.26 | Panasonic | ECE-A1EKA100 | [DigiKey](https://www.digikey.com/en/products/detail/panasonic-electronic-components/ECE-A1EKA100/6920) | [Supplier specs](https://www.digikey.com/en/products/detail/panasonic-electronic-components/ECE-A1EKA100/6920) | C3 |
| 1 µF film capacitor, 63 V | 2 | $0.74 | $1.48 | KEMET | R82DC4100SH60J | [DigiKey](https://www.digikey.com/en/products/detail/kemet/R82DC4100SH60J/11200138) | [Supplier specs](https://www.digikey.com/en/products/detail/kemet/R82DC4100SH60J/11200138) | C4, C6 |
| Green indicator LED, 5 mm THT | 1 | $0.54 | $0.54 | Kingbright | WP57GGD | [DigiKey](https://www.digikey.com/en/products/detail/kingbright/WP57GGD/3084164) | [Supplier specs](https://www.digikey.com/en/products/detail/kingbright/WP57GGD/3084164) | D1 |
| Red indicator LED, 5 mm THT | 1 | $0.42 | $0.42 | Lite-On | LTL-307ELC | [DigiKey](https://www.digikey.com/en/products/detail/liteon/LTL-307ELC/3198480) | [Supplier specs](https://www.digikey.com/en/products/detail/liteon/LTL-307ELC/3198480) | D2 |
| Yellow debug LED, 5 mm THT | 1 | $0.23 | $0.23 | Kingbright | WP7113YD | [DigiKey](https://www.digikey.com/en/products/detail/kingbright/WP7113YD/1747683) | [Supplier specs](https://www.digikey.com/en/products/detail/kingbright/WP7113YD/1747683) | D3 |
| DC barrel jack, 5.5×2.1 mm, THT | 1 | $0.75 | $0.75 | Same Sky | PJ-202A | [DigiKey](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/PJ-202A/252007) | [Supplier specs](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/PJ-202A/252007) | J1 |
| Team interface, 2×4 THT header, 2.54 mm | 1 | $1.04 | $1.04 | Sullins | PBC04DAAN | [DigiKey](https://www.digikey.com/en/products/detail/sullins-connector-solutions/PBC04DAAN/861062) | [Supplier specs](https://www.digikey.com/en/products/detail/sullins-connector-solutions/PBC04DAAN/861062) | J2 |
| UART upstream, 2-pin THT header, 2.54 mm | 1 | $0.25 | $0.25 | Sullins | PBC02SAAN | [DigiKey](https://www.digikey.com/en/products/detail/sullins-connector-solutions/PBC02SAAN/859623) | [Header spec](https://media.digikey.com/pdf/Data%20Sheets/Sullins%20PDFs/PBC02SAAN.pdf) | J3 |
| UART downstream, 2-pin THT header, 2.54 mm | 1 | $0.25 | $0.25 | Sullins | PBC02SAAN | [DigiKey](https://www.digikey.com/en/products/detail/sullins-connector-solutions/PBC02SAAN/859623) | [Header spec](https://media.digikey.com/pdf/Data%20Sheets/Sullins%20PDFs/PBC02SAAN.pdf) | J4 |
| GPIO expansion, 6-pin THT header, 2.54 mm | 1 | $0.60 | $0.60 | Sullins | PBC06SAAN | [DigiKey](https://www.digikey.com/en/products/detail/sullins-connector-solutions/PBC06SAAN/859627) | [Supplier specs](https://www.digikey.com/en/products/detail/sullins-connector-solutions/PBC06SAAN/859627) | J5 |
| E-stop wiring, 2-pin THT header, 2.54 mm | 1 | $0.25 | $0.25 | Sullins | PBC02SAAN | [DigiKey](https://www.digikey.com/en/products/detail/sullins-connector-solutions/PBC02SAAN/859623) | [Header spec](https://media.digikey.com/pdf/Data%20Sheets/Sullins%20PDFs/PBC02SAAN.pdf) | J6 |
| Buzzer-enable 2-pin header + shorting shunt | 1 | $0.35 | $0.35 | Sullins | PBC02SAAN + SPC02SYAN | [DigiKey](https://www.digikey.com/en/products/detail/sullins-connector-solutions/PBC02SAAN/859623) | [Jumper shunt](https://www.digikey.com/en/products/detail/sullins-connector-solutions/SPC02SYAN/76375) | JP1 |
| Twist-reset E-stop, NC contact, panel mount | 1 | $44.85 | $44.85 | E-Switch | E100-R11-H1KR | [DigiKey](https://www.digikey.com/en/products/detail/e-switch/E100-R11-H1KR/24614864) | [Supplier specs](https://www.digikey.com/en/products/detail/e-switch/E100-R11-H1KR/24614864) | SW1 |
| Momentary SPST-NO tactile pushbutton, THT | 2 | $0.21 | $0.42 | E-Switch | TL1105F160Q | [DigiKey](https://www.digikey.com/en/products/detail/e-switch/TL1105F160Q/5794) | [Supplier specs](https://www.digikey.com/en/products/detail/e-switch/TL1105F160Q/5794) | SW2, SW3 |
| Through-hole miniature physical test points | 7 | $0.27 | $1.89 | Keystone | 5000 | [DigiKey](https://www.digikey.com/en/products/detail/keystone-electronics/5000/255326) | [Supplier specs](https://www.digikey.com/en/products/detail/keystone-electronics/5000/255326) | TP1, TP2, TP3, TP4, TP5, TP6, TP8 |
| External 9 V DC wall adapter (assembly supply) | 1 | $10.53 | $10.53 | Tensility | 16-00134 | [DigiKey](https://www.digikey.com/en/products/detail/tensility-international-corp/16-00134/10324425) | [Supplier listing](https://www.digikey.com/en/products/detail/tensility-international-corp/16-00134/10324425) | External |

**Complete catalogue reference total: $82.02.** The estimate includes the $10.61 replacement value of a lab-supplied Nano and a $44.85 suggested industrial emergency-stop switch. Actual out-of-pocket cost may differ.

## Part 2 — Bill of Materials (Image)

![BOM RevC screenshot](EGR304_BOM_RevC.png)

*Figure 1. Screenshot of the same RevC BOM.*

## Check before ordering

- Confirm pinouts/footprints of the barrel jack, fuse, headers, and safety switch. The E-stop must use the **NC** contact.
- RevC lists 1 kΩ resistors at R3/R4/R5/R8, while the earlier power budget used provisional 330 Ω LED resistors; reconcile before assembly.
- A 910 Ω preload is not in the RevC schematic, so it is not in this BOM.
- Breadboard, hookup wire, mating connectors, USB cable and shipping are not costed here. Seven optional physical probe loops are included as test-point candidates.

[Earlier Component Selection](https://github.com/idtrfmnhcw/idtrfmnhcw_EGR304_F26.github.io/blob/main/docs/02-Component-Selection/Component-Selection.md).
