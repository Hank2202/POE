---
theme: "night"
transition: 'convex'
title: 'PSU'
---

POE 8
# Step-down PSU
Johan Paul

---

## Setup
![External Image](https://github.com/Hank2202/POE/blob/master/PSU_task.png?raw=true)

--

$V_{in}=14V-19V$

$V_{ref}=1.25V$

$f_s=33kHz$

$V_o=9V$

$I_o=0.5A$

$V_{opp(ripple)}<60mV_{pp}$

---

## Timing

Period time

$T=t_{on}+t_{off}=\frac{1}{f_s}=\frac{1}{33kHz}=30.303\mu S$

Ration between on and off time

$\frac {t_{on}}{t_{off}} = \frac {V_{out}+V_F}{V_{in(min)}-V_{sat}-V_{out}}= \frac {9+0.3}{14-1.3-9} =2.5135$


--

## Timing



$t_{off}= \frac {t_{on}+t_{off}}{\frac {t_{on}}{t_{off}}+1}=\frac {30.303}{2.5135+1}=8.624 \mu S$

On time

$t_{on}=(t_{on}+t_{off})-t_{off}=30.303-8.624=21.679\mu S$ 

Duty cycle

$D=\frac{t_{on}}{t_{on}+t_{off}}=\frac {21.679}{30.303}=0.715$

---

Peak current during switching

$I_{pk(switch)}=I_{o}*2=1A$

Value of a capacitor

$C_T = 4 * 10^{-5} * t_{on}=8.67 * 10^{-10} \Rightarrow 1\nu F$

Value of a source resistor

$R_{sc} = \frac {V_f}{I_{pk(switch)}}=\frac {0.3V}{1}=0.333 \Omega$

---

Minimal value of the inducor

$L_{min} = \frac {V_{in(min)}-V_{sat}-V_{out}}{I_{pk(switch)}}*t_{on} = \frac {14-1.3-9}{1} * 21 * 10^-6 = 77 \mu H$

Value of a $C_O$

$C_0 = \frac {I_{pk(switch)}+(t_{on}+t_{off})}{8 * V_{ripple(pp)}} = \frac {1A * 30.303\mu S}{8 * 10.8mV} = 350\mu F$

Value of a capacitor $C_{inpp}$

$C_{inpp}= \frac {I_{out}(D-D^2)}{V_{inpp(c)} * F_{sw}}=\frac{0.5(0.715 * 0.715^2)}{2.5 * 33kHz}=1.2\mu F$
