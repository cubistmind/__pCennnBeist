# DC-DC Buck Converter (XL4015)
<img width="1656" height="928" alt="xl4015-buck-converter" src="https://github.com/user-attachments/assets/09e384bd-ffe7-449b-ba7c-8ab7de452837" />
<img width="1656" height="928" alt="xl4015-buck-converter_backside" src="https://github.com/user-attachments/assets/69ed727c-bf12-4ba5-aca7-0740d61769b1" />

An adjustable step-down (buck) DC-DC converter PCB built around the XL4015 switching regulator. Designed in KiCad 10.

## Specs

| Parameter | Value |
|---|---|
| Topology | Buck (step-down), non-synchronous |
| Regulator IC | XL4015 |
| Input voltage | Up to 36V DC |
| Output voltage | Adjustable via onboard trim pot |
| Switching frequency | 180 kHz |
| Max output current | 5A (thermal/layout dependent) |
| Board | 2-layer |


## Key components

| Ref | Part | Value |
|---|---|---|
| U1 | XL4015 | Buck regulator, TO-263-5 |
| L1 | Power inductor | 47 µH / 5A |
| D1 | Schottky diode | MBDR1045G (freewheeling/catch diode) |
| CIN1 | Input capacitor | 220 µF / 50V |
| COUT1 | Output capacitor | 470 µF / 35V |
| R1 | Trim potentiometer | 3.3 kΩ (output voltage adjust) |
| R2 | Resistor | 10 kΩ (feedback divider) |
| J1 | Input connector | 2-pin screw terminal |
| J2 | Output connector | 2-pin screw terminal |

## Repo contents

- `xl4015-buck-converter.kicad_pro` — KiCad project file
- `xl4015-buck-converter.kicad_sch` — Schematic
- ` xl4015-buck-converter.kicad_pcb` — PCB layout
- `xl4015-buck-converter.zip` — Gerbers / fabrication files

## Building the board

1. Open `xl4015-buck-converter.kicad_pro` in KiCad 10.
2. Run DRC (**Inspect → Design Rules Checker**) and review any outstanding warnings before ordering.
3. Generate fabrication files: **File → Plot** for Gerbers, then **Generate Drill Files** for the Excellon drill file.
4. Send the Gerber + drill package to your board house (2-layer, standard 1.6mm thickness works with the default footprints).

## Usage

1. Connect your DC input source to J1, respecting polarity.
2. Before connecting a load, power the board and measure the output voltage at J2 with a multimeter.
3. Adjust R1 to set the desired output voltage.
4. Connect your load to J2 once the output is verified.

**Note:** this is a non-isolated converter — input and output share a common ground. Confirm your input voltage stays within the input capacitor and IC ratings before powering it up.

## License

*(Add a license here — e.g. MIT for the design files, or CERN-OHL if you want an open-hardware-specific license.)*
