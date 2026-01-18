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
