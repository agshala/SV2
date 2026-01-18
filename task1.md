# Task 1

## 1. Berechnung theoretische Resonanzfrequenz (f_0)
Gegeben:

- U = 1 V  
- R = 500 Ω  
- L = 10 mH = 0.01 H  
- C = 100 nF = 1 · 10⁻⁷ F  

Formel (Folie 5):

f₀ = 1 / (2π√(LC))

Berechnung:

LC = 0.01 · 1 · 10⁻⁷ = 1 · 10⁻⁹  
√(LC) = √(10⁻⁹) = 3.162 · 10⁻⁵  

f₀ = 1 / (2π · 3.162 · 10⁻⁵)  
f₀ ≈ 5033 Hz ≈ 5.03 kHz  

Die theoretische Resonanzfrequenz beträgt somit:

f₀ ≈ 5.03 kHz

## 2. Aufbau im Falstad-Simulator
![Task1Falstad](https://raw.githubusercontent.com/agshala/SV2/main/task_1falstad.png)

## 3. Frequenz im Simulator
Die Frequenz im Simulator beträgt ca. 5 kHz.

## 4. Vergleich
Theorie und Simulation stimmen überein. Bei Resonanz ist die Impedanz minimal und der Strom maximal.



# Task 2 – Güte eines Reihenschwingkreises

## Ziel
Untersuchung des Einflusses des Widerstands R (Dämpfung) auf die Schärfe der
Resonanzkurve (Güte Q) eines Reihenschwingkreises gemäß Folie 9.

## Aufbau im Falstad-Simulator
Reihenschwingkreis mit folgenden Werten:
- Spule: L = 20 mH  
- Kondensator: C = 10 nF  
- Widerstand: R variabel (10 Ω – 1000 Ω)  
- AC-Spannungsquelle: U = 1 V  
- Frequenz: f ≈ 11 kHz (Resonanzfrequenz)

Der Widerstand wurde mit einem Schieberegler variiert, während die Stromstärke
(im Falstad durch die Geschwindigkeit der gelben Ladungspunkte) beobachtet wurde.

## Simulation (GIF)
![Resonanzkurve bei variierendem Widerstand](https://raw.githubusercontent.com/agshala/SV2/main/task2_resonanz.gif)

## Beobachtung

- Bei kleinem Widerstand (z.B. R ≈ 10 Ω):
  - Sehr hohe Stromamplitude
  - Sehr scharfe und schmale Resonanz
  - Kleine Bandbreite
  - Große Güte Q

- Bei größerem Widerstand (z.B. R ≈ 300 Ω – 1000 Ω):
  - Deutlich kleinere Stromamplitude
  - Resonanzkurve wird flacher und breiter
  - Größere Bandbreite
  - Kleinere Güte Q

## Theoretischer Zusammenhang

Für den Reihenschwingkreis gilt:

Q = ω₀ · L / R

mit  
ω₀ = 2πf₀ (Kreisresonanzfrequenz)

Daraus folgt:
- R ↑  ⇒  Q ↓  
- R ↑  ⇒  Bandbreite ↑  
- R ↓  ⇒  Q ↑  
- R ↓  ⇒  Bandbreite ↓  

## Fazit

Die Simulation bestätigt die Aussage aus Folie 9:

**Je größer die Güte Q, desto schmaler ist die Resonanzkurve und desto kleiner ist die Bandbreite.**  
Ein größerer Widerstand führt zu stärkerer Dämpfung, geringerer Güte und einer
breiteren, flacheren Resonanzkurve.




# Task 3 – LC-Bandpass und LC-Bandsperre

## 1. Theoretische Resonanzfrequenz

Gegeben:

- L = 1 mH = 1 · 10⁻³ H  
- C = 10 nF = 1 · 10⁻⁸ F  

Thomsonsche Formel:

f₀ = 1 / (2π√(LC))

Berechnung:

LC = 1 · 10⁻³ · 1 · 10⁻⁸ = 1 · 10⁻¹¹  
√(LC) = 3.16 · 10⁻⁶  

f₀ ≈ 1 / (2π · 3.16 · 10⁻⁶)  
f₀ ≈ 50.3 kHz  

Die theoretische Resonanzfrequenz beträgt somit ca. **50 kHz**.

---

## 2. Aufbau 1 – Bandpass (Parallelschwingkreis als Ausgang)

Schaltung:

- Vorwiderstand Ri = 2.2 kΩ
- Parallelschwingkreis aus:
  - L = 1 mH
  - C = 10 nF
- Ausgangsspannung am Parallelschwingkreis

GIF des Frequenzgangs:

![Bandpass](https://raw.githubusercontent.com/agshala/SV2/main/task3_1.gif)

Beobachtung:
Bei ca. 50 kHz erreicht die Ausgangsspannung ihr Maximum.

---

## 3. Aufbau 2 – Bandsperre (Serienschwingkreis parallel zum Ausgang)

Schaltung:

- Ausgangswiderstand R2 = 2.2 kΩ
- Serien-LC-Zweig:
  - L = 1 mH
  - C = 10 nF
- Serien-LC liegt parallel zu R2

GIF des Frequenzgangs:

![Bandsperre](https://raw.githubusercontent.com/agshala/SV2/main/task3_2.gif)

Beobachtung:
Bei ca. 50 kHz fällt die Ausgangsspannung stark ab (Kerbe / Notch).

---

## 4. Vergleich und Erklärung

### Bestätigung der Resonanzfrequenz
Die Simulation zeigt bei beiden Schaltungen ein Extremum bei ca. **50 kHz**, was den berechneten Wert bestätigt.

### Gegensätzliches Verhalten

| Schaltung | Verhalten bei f₀ |
|------------|------------------|
| Bandpass (Parallel-LC) | Maximale Ausgangsspannung |
| Bandsperre (Serien-LC) | Minimale Ausgangsspannung |

### Physikalische Erklärung (Impedanz)

- **Parallelschwingkreis bei f₀:**
  - Gesamtimpedanz maximal (nahezu offen)
  - Kaum Strom fließt
  - Spannung fällt vollständig am LC-Kreis ab  
  → Spannung am Ausgang wird maximal (Bandpass).

- **Serienschwingkreis bei f₀:**
  - Gesamtimpedanz minimal (nahezu Kurzschluss)
  - Der LC-Zweig leitet stark nach Masse
  - Ausgangsspannung wird kurzgeschlossen  
  → Spannungseinbruch (Bandsperre / Notch).

---

## 5. Schlussfolgerung

Obwohl beide Schaltungen identische L- und C-Werte besitzen, erzeugt allein die Verschaltung:

- Parallel-LC → hohe Impedanz bei Resonanz → Spannungsmaximum  
- Serien-LC → niedrige Impedanz bei Resonanz → Spannungsauslöschung  

Damit ist der fundamentale Unterschied zwischen **Bandpass** und **Bandsperre** bestätigt.








# Task 4 – 3-Bit D/A-Wandler (R-2R-Leiternetzwerk)

## 1. Ziel
Ziel dieser Aufgabe ist es, das Grundprinzip eines Digital-Analog-Wandlers (DAC) zu verstehen.  
Ein 3-Bit DAC mit einem R-2R-Widerstandsnetzwerk wandelt ein digitales Wort (000 bis 111) in eine analoge Ausgangsspannung um. Dies ist der inverse Prozess zur Quantisierung in der PCM (siehe Folie 30).

## 2. Aufbau

Bauteile:
- Referenzspannung: Vref = 10 V (DC-Quelle)
- Widerstände: R = 1 kΩ, 2R = 2 kΩ
- 3 Umschalter (SPDT) für die Bits:
  - Bit 2 (MSB)
  - Bit 1
  - Bit 0 (LSB)

Die Umschalter verbinden die jeweiligen Knoten des R-2R-Netzwerks entweder mit:
- 10 V (logische 1) oder
- 0 V / Masse (logische 0)

Der Ausgang wird am rechten Ende der R-2R-Leiter abgegriffen und mit einem Voltmeter bzw. Scope (DC Level) gemessen.

## 3. Theoretische Schrittgröße

Für einen idealen 3-Bit DAC gilt:

ΔU = Vref / 2ⁿ = 10 V / 8 = 1.25 V

Damit sollte jeder digitale Zählerschritt die Ausgangsspannung um konstant 1.25 V erhöhen.

## 4. Messwerttabelle (Simulation)

| Bit 2 (MSB)  | Bit 1 | Bit 0 (LSB) | Dezimalwert | Uaus (V) |
|--------------|-------|-------------|-------------|----------|
| 0            | 0     | 0           | 0           | 0.0      |
| 0            | 0     | 1           | 1           | 1.7      |
| 0            | 1     | 0           | 2           | 2.0      |
| 0            | 1     | 1           | 3           | 2.4      |
| 1            | 0     | 0           | 4           | 2.5      |
| 1            | 0     | 1           | 5           | 3.0      |
| 1            | 1     | 0           | 6           | 3.1      |
| 1            | 1     | 1           | 7           | 3.3      |

## 5. Simulation (GIF)

![3-Bit DAC R-2R](https://raw.githubusercontent.com/agshala/SV2/main/task4.gif)

Das GIF zeigt, wie die drei Schalter von 000 bis 111 umgeschaltet werden und die Ausgangsspannung stufenförmig ansteigt.

## 6. Auswertung

### Beobachtung
Die Ausgangsspannung steigt beim Umschalten der Binärkombinationen stufenförmig an und bildet eine Treppenfunktion.  
Damit wird das Grundprinzip der Digital-Analog-Wandlung und der Quantisierung sichtbar.

### Schrittgröße
Die gemessenen Spannungsdifferenzen zwischen den einzelnen Stufen sind nicht exakt konstant, liegen jedoch im gleichen Größenbereich.  
Abweichungen von der idealen Schrittweite (1.25 V) entstehen durch:

- endliche Innenwiderstände,
- Belastung des R-2R-Netzwerks,
- numerische Effekte der Simulation.

### Erklärung (Bezug zu Folie 30)
Das R-2R-Netzwerk realisiert eine binäre Gewichtung der Bits:

- Das MSB trägt den größten Spannungsanteil bei,
- das nächste Bit etwa die Hälfte davon,
- das LSB den kleinsten Anteil.

Durch die Kombination dieser gewichteten Beiträge entstehen diskrete Spannungsstufen.  
Dies entspricht exakt der Quantisierung eines analogen Signals in der PCM, bei der ein kontinuierlicher Wertebereich in diskrete Amplitudenstufen zerlegt wird.
