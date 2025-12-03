Analog Slot Machine – 3-Digit Random Number Generator
=====================================================

This project is a fully discrete, CMOS-based 3-digit “slot machine” random number
generator designed in KiCad. A transistor noise source, analog amplification, and a
comparator generate a pseudo-random clock that drives three CD4026 decade counters and
Expand
Slot_Machine_description.txt
5 KB

Analog Slot Machine – 3-Digit Random Number Generator
=====================================================

This project is a fully discrete, CMOS-based 3-digit “slot machine” random number
generator designed in KiCad. A transistor noise source, analog amplification, and a
comparator generate a pseudo-random clock that drives three CD4026 decade counters and
7-segment LED displays. There is no microcontroller involved.

In normal use:
- A 2N3904 transistor is biased so it produces broadband electronic noise.
- An LM358 dual op-amp amplifies that noise and also creates a mid-supply reference (V_REF).
- An LM393 comparator compares the noisy signal to V_REF and outputs a pseudo-random
  digital clock (CLK).
- CD4013 flip-flops and a CD4081 AND gate handle the RUN state and decide when CLK is
  allowed through.
- Three CD4026 counters drive three 7-segment LED displays (e.g. 5161AS), forming a
  3-digit readout.
- When you hold the RUN pushbutton, the digits “spin”; when you release it, the
  current 3-digit number is frozen on the display.
- The whole circuit runs from a single 9 V battery (PP3).


Hardware Architecture
---------------------

1) Power and Decoupling
- Input is a 9 V battery, with VDD and GND as the main rails.
- Each IC has a 100 nF ceramic capacitor close to its power pins to keep the supply
  clean at high frequencies.
- Electrolytic capacitors on the 9 V rail provide bulk smoothing and help with
  startup and transients.
- This keeps both the analog and digital blocks stable and less sensitive to noise.


2) Noise and Clock Generation
- A 2N3904 NPN transistor is biased in a regime where it naturally produces broadband
  electronic noise. High-value resistors and a small capacitor shape this noise a bit.
- The LM358 op-amp does two jobs:
  - One channel generates V_REF, roughly at mid-supply.
  - The other channel amplifies and band-limits the noise so the comparator sees a
    clean, usable signal.
- The LM393 comparator compares the amplified noise to V_REF:
  - Whenever the noise crosses the reference, the comparator output toggles.
  - This produces a jittery, pseudo-random digital clock signal (CLK), which becomes
    the timing source for the counters.


3) Run / Sync Control and Clock Gating
- A CD4013 dual D-type flip-flop stores the RUN state and any related control bits.
- A dual-pole momentary RUN pushbutton, along with a few diodes and resistors,
  generates clean set/reset and edge-detect pulses so the flip-flop behaves nicely.
- A CD4081 quad 2-input AND gate combines:
  - The random clock (CLK),
  - The RUN state,
  - And any extra gating signals used per digit.
- When RUN is active, CLK passes through the AND gates and reaches the CD4026 counters.
- When RUN is inactive, the clock path is cut off and the counters simply hold their
  last values.
- An SPDT switch is available to select between different modes (for example,
  changing how reset or test behavior works), depending on how you choose to wire it.


4) Counters and Display
- Three CD4026 decade counters are used, one for each decimal digit:
  - Each counter receives a gated clock input from the CD4081, plus reset and control
    wiring for predictable startup.
  - CD4026 devices include built-in 7-segment decoding, so no extra decoder IC is needed.
- Three 7-segment LED displays (such as 5161AS) are driven directly from the CD4026
  outputs through current-limiting resistors (about 2.2 kΩ per segment).
- Together they form a simple 3-digit decimal display:
  - While you hold RUN, the digits advance quickly and look like spinning reels.
  - When you release RUN, the clock stops and the last 3-digit number stays on the
    display until the next run.


Usage
-----

- Open the KiCad project to inspect the schematic and PCB layout.
- If you want a physical board, generate Gerber and drill files from the KiCad PCB
  and send them to a PCB manufacturer.
- Assemble the board starting with resistors and capacitors, then sockets and
  connectors, and finally the ICs and displays.
- After soldering, check that the power rails are correct and there are no shorts
  between VDD and GND.
- Connect a 9 V battery.
- Press and hold the RUN button: the digits should spin rapidly.
- Release RUN: a random 3-digit number should remain displayed.