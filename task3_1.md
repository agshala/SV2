# Task 3 – LC-Bandpass und Bandsperre

## 1. Ziel
Untersuchung des fundamentalen Unterschieds zwischen einem Bandpassfilter und einem Bandsperrfilter mit identischen L/C-Werten, jedoch unterschiedlicher Verschaltung.

## 2. Gegebene Werte

- Spule: L = 1 mH = 1 · 10⁻³ H  
- Kondensator: C = 10 nF = 1 · 10⁻⁸ F  
- Eingangswiderstand (Bandpass): Ri = 2.2 kΩ  
- Ausgangswiderstand (Bandsperre): R2 = 2.2 kΩ  


## 3. Theoretische Resonanzfrequenz

Thomsonsche Formel:

\[
f_0 = \frac{1}{2\pi\sqrt{LC}}
\]

\[
f_0 = \frac{1}{2\pi\sqrt{1\cdot10^{-3} \cdot 1\cdot10^{-8}}}
\]

\[
f_0 \approx 50 \text{ kHz}
\]


## 4. Aufbau 1 – Bandpass (Parallelschwingkreis)

Ein Parallelschwingkreis aus L und C liegt am Ausgang hinter dem Serienwiderstand Ri.

![Bandpass-Frequenzgang](https://raw.githubusercontent.com/agshala/SV2/main/task3_1.gif)

**Beobachtung:**  
Bei der Resonanzfrequenz von ca. 50 kHz erreicht die Ausgangsspannung ihr Maximum.

---

## 5. Aufbau 2 – Bandsperre (Reihenschwingkreis)

Ein Reihenschwingkreis aus L und C liegt parallel zum Ausgangswiderstand R2.

*(Hier dein zweites GIF einfügen, z.B.: task3_2.gif)*

```markdown
![Bandsperre-Frequenzgang](https://raw.githubusercontent.com/agshala/SV2/main/task3_2.gif)
