Numton
kornny
🤓 LMAO

TeXit
APP
 — 11/29/2025 7:27 PM
Numton
Image
Numton — 11/29/2025 7:28 PM
For each integer $n \ge 1$, let $\mathcal{O}(n)$ be the set of all positive integers $L$
for which there exists a permutation of ${1,2,\dots,n}$ whose order is $L$.
Determine all $n$ for which $\mathcal{O}(n)$ is of the form ${1,2,\dots,M}$ for some $M$.
TeXit
APP
 — 11/29/2025 7:28 PM
Numton
Image
Numton — 11/29/2025 7:32 PM
For a permutation $\sigma$ of a finite set, define the \emph{order} of $\sigma$ to be the smallest
positive integer $k$ such that $\sigma^k$ is the identity permutation. For each positive integer $n$, let $\mathcal{O}(n)$ be the set of all positive integers $L$
for which there exists a permutation of $\{1,2,\dots,n\}$ whose order is $L$.
Determine all $n$ for which $\mathcal{O}(n)$ is of the form $\{1,2,\dots,M\}$ for some positive integer $M$. 
TeXit
APP
 — 11/29/2025 7:33 PM
Numton
Image
Numton — 11/29/2025 7:36 PM
For each $n\in\mathbb{N}$, define $$x_n \;=\; 1 + \cfrac{1}{2 + \cfrac{1}{3 + \cfrac{1}{\ddots + \cfrac{1}{n}}}}.$$ Prove that for all distinct positive integers $m,n$, $$|x_m - x_n| \;<\; \dfrac{1}{\bigl(\min\{m,n\}!\bigr)^2}.$$
TeXit
APP
 — 11/29/2025 7:36 PM
Numton
Image
Numton — 11/30/2025 1:21 AM
For a permutation $\sigma$ of a finite set, define the \emph{order} of $\sigma$
to be the smallest positive integer $k$ such that $\sigma^k$ is the identity
permutation. For each positive integer $n$, consider all permutations of
$\{1,2,\dots,n\}$ and the positive integers that occur as their orders.

Determine all $n$ for which there exists a positive integer $M$ such that
\begin{itemize}
    \item for every integer $k$ with $1 \le k \le M$, there exists a permutation
    of $\{1,2,\dots,n\}$ whose order is $k$, and
    \item no permutation of $\{1,2,\dots,n\}$ has order greater than $M$.
\end{itemize}
TeXit
APP
 — 11/30/2025 1:21 AM
Numton
Image
Numton — 11/30/2025 8:04 AM
For each $n\in\mathbb{N}$, define $$x_n = 1 + \dfrac{1}{2 + \dfrac{1}{3 + \cdots + \dfrac{1}{n}}}.$$ Prove that there exists a real number $x$ such that, for every $n\in\mathbb{N}$, $$|x - x_n| < \dfrac{1}{(n!)^2}.$$ 
TeXit
APP
 — 11/30/2025 8:05 AM
Numton
Image
Numton — 11/30/2025 8:21 AM
Define the \emph{order} of a permutation $\sigma$ of $\{1,2,\dots,n\}$ to be the least positive integer $k$ such that
        \[\sigma^k(m) = m \quad \text{for all } m = 1,2,\dots,n.\]
        For each integer $n \ge 1$, let $\mathcal{O}(n)$ be the set of all positive integers that occur as the order of some permutation of $\{1,2,\dots,n\}$. Determine all $n$ for which there exists $M \in \mathbb{N}$ such that \[\mathcal{O}(n) = \{1,2,\dots,M\}.\]
TeXit
APP
 — 11/30/2025 8:21 AM
Numton
Image
Numton — 11/30/2025 2:49 PM
Let $n \ge 3$ be an integer, and let $(a_1,\dots,a_n)$ be a permutation of ${1,2,\dots,n}$.

For each $m$ with $1 \le m \le n$ and $\gcd(m,n)=1$, define $b^{(m)}k = a{km}$ (index $km$ taken modulo $n$ and read in ${1,\dots,n}$).
A \emph{3-sweep} in the $m$-chart is a triple of consecutive terms
[
\bigl(b^{(m)}k,b^{(m)}{k+1},b^{(m)}_{k+2}\bigr)
]
(indices modulo $n$) equal to $(x,x+1,x+2)$ modulo $n$ for some integer $x$.

Let $T(m)$ be the number of 3-sweeps in the $m$-chart, and set
[
S(a_1,\dots,an)=\sum{\substack{1 \le m \le n \ \gcd(m,n)=1}} T(m).
]

Determine the maximum possible value of $S(a_1,\dots,a_n)$.
TeXit
APP
 — 11/30/2025 2:49 PM
Numton
Image
Numton — 11/30/2025 9:39 PM
Let $n \ge 3$ be an integer and consider maimai gameplay on $n$ buttons placed at the vertices of a regular $n$-gon of radius $1$. A chart is a permutation $\sigma$ of $\{1,\dots,n\}$. Two hands play the chart, each hand starts off-screen with initial cost $0$ and then moves along straight line segments between the buttons it hits. For each permutation $\sigma$, let $P(\sigma)$ be the minimal possible total Euclidean distance traveled by both hands over all assignments of the notes of $\sigma$ to the two hands. Define
$$F(n) = \max_{\sigma} P(\sigma),$$
where the maximum is taken over all permutations $\sigma$ of $\{1,\dots,n\}$. Prove or disprove that there exists a constant $L > 0$ such that
$$\lim_{n \to \infty} \frac{F(n)}{n} = L.$$ 
TeXit
APP
 — 11/30/2025 9:43 PM
Numton
Image
Numton — Yesterday at 1:02 AM
#  | Reference                                                                                               | Qty | Value        | Footprint                                                     | DNP
---+---------------------------------------------------------------------------------------------------------+-----+--------------+---------------------------------------------------------------+----
1  | AFF1, AFF2, AFF3                                                                                        | 3   | 5161AS       | Display_7Segment:7SegmentLED_LTS6760_LTS6780                  |    
2  | BC1                                                                                                     | 1   | 2N3904       | Package_TO_SOT_THT:TO-92_Inline                               |    
3  | BT1                                                                                                     | 1   | 9V           | Battery:BatteryHolder_MPD_BA9VPC_1xPP3                        |    
4  | C1, C2, C4, C5, C7, C8, C10, C11, C16, C17, C18                                                         | 11  | 100n         | Capacitor_THT:C_Disc_D5.0mm_W2.5mm_P5.00mm                    |    
Expand
BOM_table.txt
6 KB
Numton — Yesterday at 4:23 AM
ICs:
- 1× CD40106
- 1× LM358
- 1× CD4013
- 1× LM393
- 1× CD4081
- 3× CD4026

Displays:
- 3× 7-segment LED (5161AS)

Transistor & Diodes:
- 1× 2N3904
- 4× 1N4148

Capacitors:
- 11× 100 nF
- 1× 1 nF
- 1× 100 pF
- 1× 10 nF
- 3× 4.7 µF electrolytic
- 1× 47 µF electrolytic

Resistors:
- 2× 22 kΩ
- 2× 1 MΩ
- 2× 1 kΩ
- 2× 100 kΩ
- 1× 10 kΩ
- 1× 150 kΩ
- 1× 330 kΩ
- 1× 470 kΩ
- 21× 2.2 kΩ

Switches & Power:
- 1× momentary pushbutton
- 1× SPDT slide switch
- 1× 9 V battery holder
https://chatgpt.com/share/692d8a28-c0a4-8004-98ea-bef6ed6ca42b
ChatGPT
ChatGPT - Study plan for song
Shared via ChatGPT
Image
Numton — Yesterday at 5:05 AM
Image
Image
Numton — Yesterday at 9:19 AM
https://ece.ucsd.edu/undergraduate/srip-2026
Numton — Yesterday at 11:51 AM
https://artofproblemsolving.com/community/c6h3725419_some_thoughts_on_how_i_create_olympiad_problems
Numton
 pinned a message to this channel. See all pinned messages. — Yesterday at 12:59 PM
Numton — Yesterday at 1:56 PM
C6 to 330pF works 
Numton — Yesterday at 2:07 PM
AFF1  5161AS
AFF2  5161AS
AFF3  5161AS

BC1   2N3904
BT1   9V battery holder

C1    100n
C2    100n
C3    1n
C4    100n
C5    100n
C6    330p
C7    100n
C8    100n
C9    47p
C10   100n
C11   100n
C12   47u
C13   4.7u
C14   4.7u
C15   4.7u
C16   100n
C17   100n
C18   100n

D1    1N4148
D2    1N4148
D3    1N4148
D4    1N4148

R1    22k
R2    22k
R3    1M
R4    1k
R5    100k
R6    1M
R7    1k
R8    100k
R9    10k
R10   150k
R11   330k
R12   470k
R13   2.2k
R14   2.2k
R15   2.2k
R16   2.2k
R17   2.2k
R18   2.2k
R19   2.2k
R20   2.2k
R21   2.2k
R22   2.2k
R23   2.2k
R24   2.2k
R25   2.2k
R26   2.2k
R27   2.2k
R28   2.2k
R29   2.2k
R30   2.2k
R31   2.2k
R32   2.2k
R33   2.2k

SW1   SW_Push_Dual
SW2   SW_SPDT

U1    40106
U2    LM358
U3    4013
U4    LM393
U5    4081
U6    4026
U7    4026
U8    4026 
Numton — Yesterday at 10:54 PM
Attachment file type: acrobat
Slot_Machine.pdf
335.70 KB
Numton — 2:12 AM
Let $\mathbb{N} = {1,2,3,\dots}$. Find all functions $f:\mathbb{N}\to\mathbb{N}$ such that $f(1) = 1$
and for all positive integers $m,n$, $$f(m + f(n)) = f(m) + n.$$ 
TeXit
APP
 — 2:13 AM
Numton
Image
Numton — 2:23 AM
Image
Image
Image
Numton — 7:58 AM
Let $\mathbb{Z}$ be the set of all integers. Find all functions $f : \mathbb{Z} \to \mathbb{Z}$ such that for all integers $m,n$,
[
f\bigl(m + f(n)\bigr) = f(m) + n.
]
TeXit
APP
 — 7:58 AM
Numton
Image
Numton — 8:21 AM
Find all functions $f : \mathbb{R} \to [0,\infty)$ such that for all real numbers $x,y$ and all positive integers $k$, the following hold:
\begin{enumerate}
    \item $f(x) = 0 \text{if and only if} x = 0$.
    \item $f(x) = f(-x)$.
    \item $f(x+y) \le f(x) + f(y)$.
    \item $f(kx) = k,f(x)$.
    \item For every $\varepsilon > 0$, there exists $\delta > 0$ such that if $|x| < \delta$ then $f(x) < \varepsilon$.
\end{enumerate} 
TeXit
APP
 — 8:21 AM
Numton
Image
Numton — 8:56 AM
Find all functions $f : \mathbb{R} \to [0,\infty)$ such that for all real numbers $x,y$ and all positive integers $k$, the following hold:
\begin{enumerate}
    \item $f(x) = 0 \text{ if and only if } x = 0$.
    \item $f(x) = f(-x)$.
    \item $f(x+y) \le f(x) + f(y)$.
    \item $f(kx) = kf(x)$.
    \item For every $\varepsilon > 0$, there exists $\delta > 0$ such that if $|x| < \delta$ then $f(x) < \varepsilon$.
\end{enumerate} 
TeXit
APP
 — 8:57 AM
Numton
Image
Numton
 pinned a message to this channel. See all pinned messages. — 10:00 AM
Numton — 5:16 PM
C6 to 47p
Numton — 5:33 PM
R9 4.7k
R3 100k
Numton — 5:47 PM
C6 to 47p
R3 to 100k
R9 to 4.7k
Numton — 6:52 PM
Image
Image
Image
Numton — 7:47 PM
Attachment file type: acrobat
ECE_17_Cheat_Sheets.pdf
4.86 MB
Let $P$ be a convex subset of the plane with $|P| = 1$. For each line $\ell$, let $P_\ell$ be the reflection of $P$ across $\ell$. Find the minimum possible value of $$\max_{\ell} |P \cap P_\ell|$$ over all such convex sets $P$. 
TeXit
APP
 — 7:53 PM
Numton
Image
Numton — 9:46 PM
Analog Slot Machine – 3-Digit Random Number Generator
=====================================================

This project is a fully discrete, CMOS-based 3-digit “slot machine” random number
generator designed in KiCad. A transistor noise source, analog amplification, and a
comparator generate a pseudo-random clock that drives three CD4026 decade counters and
Expand
Slot_Machine_description.txt
5 KB
﻿
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