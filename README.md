Analog Slot Machine – 3-Digit Random Number Generator
=====================================================

This document describes a discrete, CMOS-based 3-digit slot-machine-style random number generator. The circuit is implemented entirely with analog components and standard logic ICs (no microcontroller) and is captured in a KiCad project, with the schematic exported as Slot_Machine.pdf for reference.

The device uses a transistor noise source, analog amplification, and a comparator to generate a pseudo-random clock. This clock is gated into three CD4026 decade counters, which drive three 7-segment LED displays. A front-panel RUN pushbutton allows the user to start and stop the “spin,” leaving a random 3-digit value on the display.

----------------------------------------------------------------------
1. System Overview
----------------------------------------------------------------------

Supply:
- Single 9 V battery (PP3).

Main functional idea:
- Generate broadband electronic noise using a discrete NPN transistor.
- Amplify and shape the noise using an LM358 dual operational amplifier.
- Convert the conditioned noise into a digital pulse train using an LM393 comparator.
- Use CD4013 flip-flops and a CD4081 AND gate to implement RUN / SYNC control and clock gating.
- Drive three CD4026 decade counters, each connected to a 7-segment LED display (e.g. 5161AS or equivalent).

User interaction:
- When the RUN pushbutton is held, the displays update rapidly and resemble a slot-machine spin.
- When RUN is released, the counters stop receiving clock pulses and the last shown 3-digit value is retained.

----------------------------------------------------------------------
2. Functional Blocks
----------------------------------------------------------------------

The circuit is organized into four main functional blocks:

1) Power and Decoupling
2) Noise and Clock Generation
3) Run / Sync Control and Clock Gating
4) Counters and Display Section

Each block is summarized below.

----------------------------------------------------------------------
2.1 Power and Decoupling
----------------------------------------------------------------------

Input:
- 9 V battery connected via a battery clip and holder.

Rails:
- VDD: main positive supply rail.
- GND: reference ground.

Decoupling and filtering:
- 100 nF ceramic capacitors placed near the supply pins of each IC to provide local high-frequency decoupling.
- Electrolytic capacitors (in the µF range) used for bulk smoothing of the battery supply and to reduce transients.

This block ensures a stable supply for both the analog front end and the digital CMOS logic, improving noise performance and overall reliability.

----------------------------------------------------------------------
2.2 Noise and Clock Generation
----------------------------------------------------------------------

Noise source:
- A 2N3904 NPN transistor is biased in a high-impedance regime so that it produces broadband electronic noise.
- High-value resistors and a small capacitor form part of the noise-shaping network at the transistor node.

Analog conditioning:
- An LM358 dual operational amplifier is used.
  - One channel establishes a mid-supply reference voltage (V_REF).
  - The second channel amplifies and band-limits the noise signal so that it has suitable amplitude and spectral content for the comparator input.
- Feedback resistors and capacitors set the gain and bandwidth of the noise amplifier stage.

Comparator and clock:
- An LM393 dual comparator converts the analog noise into a logic-level clock signal.
  - The amplified noise is compared to V_REF.
  - Each crossing of the noise signal relative to V_REF generates transitions at the comparator output.
- The resulting signal is a pseudo-random digital pulse train, referred to as CLK, which serves as the system clock for the counters. This clock is later gated by the control logic.

----------------------------------------------------------------------
2.3 Run / Sync Control and Clock Gating
----------------------------------------------------------------------

State storage:
- A CD4013 dual D-type flip-flop is used to store RUN and related control states.
- The RUN state determines whether the counters are currently spinning (receiving clock pulses) or holding a value.
- Additional control lines, such as SYNC or reset signals, can be derived from the flip-flop outputs and passive networks.

User input:
- A dual-pole momentary pushbutton (RUN switch) provides the primary user control.
- Resistors and diodes form edge-detection and reset networks to ensure clean, well-defined transitions at the flip-flop inputs.

Clock gating:
- A CD4081 quad 2-input AND gate combines the noise-derived CLK with RUN and any per-digit gating signals.
- When RUN is active, the AND gates pass the clock pulses through to the CD4026 counters.
- When RUN is inactive, the clock path is blocked, freezing the counters at their current contents.

Mode selection:
- An SPDT switch can be used for alternate operating modes (for example, different run behaviors or test modes), depending on how it is wired in the schematic. This allows experimentation with different timing or reset schemes without changing the core architecture.

----------------------------------------------------------------------
2.4 Counters and Display Section
----------------------------------------------------------------------

Decade counters:
- Three CD4026 decade counters are used, one for each digit.
- Each counter receives a gated clock input, along with reset and control signals.
- The CD4026 devices provide both decade counting and integrated 7-segment decoding, simplifying the display drive.

7-segment displays:
- Three 7-segment LED displays (such as 5161AS modules) are driven directly from the CD4026 segment outputs.
- Current-limiting resistors (typically on the order of 2.2 kΩ per segment) are used to protect both the LEDs and the CD4026 outputs.
- Combined, the three displays present a 3-digit decimal value.

Visual behavior:
- While RUN is asserted, the digits advance at a rate determined by the noise-derived CLK. This gives the appearance of spinning reels.
- When RUN is released, the clock gating stops further transitions, and the counters hold their last values, providing a random 3-digit result.

----------------------------------------------------------------------
3. Typical Repository Structure
----------------------------------------------------------------------

A recommended layout for the GitHub repository is:

hardware/
  Slot_Machine.kicad_pro
  Slot_Machine.kicad_sch
  Slot_Machine.kicad_pcb

docs/
  Slot_Machine.pdf        (schematic export)
  Slot_Machine.png        (optional schematic image or block diagram)

README.md                 (project documentation based on this text)

File names can be adjusted to match the actual KiCad project.

----------------------------------------------------------------------
4. Key Components (Summary)
----------------------------------------------------------------------

Integrated circuits:
- LM358 dual operational amplifier (noise amplification and reference generation).
- LM393 dual comparator (conversion of noise into logic-level clock).
- CD40106 Schmitt-trigger inverter (if used for buffering or pulse shaping).
- CD4013 dual D-type flip-flop (RUN / SYNC state storage).
- CD4081 quad 2-input AND gate (clock gating and control logic).
- CD4026 decade counter with integrated 7-segment decoding (three units, one per digit).

Discrete semiconductors:
- 2N3904 NPN transistor (noise source).
- Signal diodes (used in reset and edge-detection networks).

Displays and passives:
- Three 7-segment LED displays (e.g. 5161AS).
- Segment current-limiting resistors.
- Bias, feedback, and pull-up / pull-down resistors throughout the design.
- 100 nF ceramic decoupling capacitors for each IC.
- Electrolytic capacitors for bulk filtering.
- Small capacitors (pF–nF range) for noise shaping and timing.

----------------------------------------------------------------------
5. Assembly and Verification
----------------------------------------------------------------------

Assembly sequence (typical):
- Solder resistors, small capacitors, and other low-profile components.
- Install IC sockets, if used, and any board-mounted connectors.
- Add switches, battery connector, and 7-segment displays.
- Finally insert the ICs into their sockets after visual inspection.

Initial checks:
- Verify there are no shorts between VDD and GND.
- Confirm continuity on major power rails and critical nets.
- Inspect solder joints for bridges or cold joints.

Power-on testing:
- Connect a 9 V battery and confirm that the supply voltage is within the expected range.
- If available, use an oscilloscope to observe:
  - The noise waveform at the LM358 output.
  - The comparator output (CLK) to confirm a random pulse train.
- Press and hold the RUN button; the three digits should change rapidly.
- Release RUN; the digits should stop and hold a 3-digit value.

----------------------------------------------------------------------
6. Licensing and Contributions
----------------------------------------------------------------------

The project maintainer should specify the license under which the hardware design, schematic files, PCB layout, and any associated software are released (for example, CERN-OHL-S for hardware and MIT for accompanying scripts or tools).

Contributions are welcome. Examples include:
- Layout or routing improvements.
- Alternative noise-source implementations or measurements.
- Simulation models and test data (e.g. noise spectra, timing diagrams).
- Photographs, build notes, and usage feedback.

Proposed changes can be submitted through issues or pull requests in the GitHub repository.
