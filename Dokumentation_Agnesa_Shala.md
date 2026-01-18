# Student Information

|                   |                             |
|-------------------|-----------------------------|
| Name              | Agnesa Shala                |
| Matrikelnummer    | 223289                      |
| Studiengang       |Software Engineering Bachelor|
| Kurs              | SV2                         |
| Betreuer          | Marc Nauendorf              |
| Akademisches Jahr | 2025/2026                   |




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





# Task 5 – Filterung von Obertönen (Rechteck-zu-Sinus-Wandler)

## 1. Ziel  
Ziel dieser Aufgabe ist es, den Zusammenhang zwischen der Fourier-Analyse einer Rechteckschwingung und der Filterwirkung eines LC-Bandpassfilters zu verstehen.  
Eine Rechteckschwingung besteht aus einer Grundschwingung und ungeraden Oberschwingungen. Der Bandpass soll nur die Grundfrequenz durchlassen und die Obertöne unterdrücken, sodass am Ausgang eine sinusförmige Spannung entsteht.


## 2. Aufbau

Bauteile:
- Rechteckspannungsquelle (Square Wave)
- Frequenz: f = f₀
- Vorwiderstand: Ri = 2,2 kΩ
- Parallelschwingkreis:
  - Spule: L = 1 mH
  - Kondensator: C = 10 nF
- Bezugspotential: Masse (0 V)

Der Parallelschwingkreis (L und C) ist am Ausgang gegen Masse geschaltet.  
Die Ausgangsspannung wird am Knoten oberhalb des LC-Kreises gemessen.


## 3. Berechnung der Resonanzfrequenz

Thomsonsche Formel:

f₀ = 1 / (2π√(LC))

f₀ = 1 / (2π√(1·10⁻³ · 10·10⁻⁹))

f₀ ≈ 50,3 kHz

Die Rechteckquelle wird daher auf **50,3 kHz** eingestellt.


## 4. Simulation (GIF)

![Rechteck-zu-Sinus-Filterung](https://raw.githubusercontent.com/agshala/SV2/main/task5.gif)

Das GIF zeigt:
- das Rechtecksignal am Eingang
- das gefilterte Signal am Ausgang des LC-Bandpasses


## 5. Beobachtung

Am Eingang liegt eine Rechteckspannung mit steilen Flanken und vielen Oberwellen.  
Am Ausgang erscheint eine nahezu sinusförmige Spannung. Die hohen Frequenzanteile sind stark gedämpft, während die Grundfrequenz erhalten bleibt.


## 6. Auswertung

### Fourier-Zusammenhang  
Eine Rechteckschwingung setzt sich aus einer Grundschwingung und ungeraden Harmonischen zusammen:

f₁, 3f₁, 5f₁, 7f₁, …

### Filterwirkung  
Der LC-Bandpass besitzt bei der Resonanzfrequenz f₀ eine maximale Impedanz.  
Dadurch wird die Spannung bei f₀ verstärkt, während Frequenzen außerhalb der Bandbreite stark abgeschwächt werden.

### Erklärung  
Da die Grundfrequenz der Rechteckschwingung auf die Resonanzfrequenz des Bandpasses eingestellt wurde:

- Die Grundschwingung wird nahezu ungedämpft übertragen.
- Die Obertöne (3f₀, 5f₀, …) werden unterdrückt.

Dadurch verschwindet die kantige Form des Rechtecksignals und es bleibt eine nahezu reine Sinusschwingung übrig.


## 7. Ergebnis

Die Simulation bestätigt:

- Der LC-Bandpass filtert die Obertöne der Rechteckschwingung.
- Nur die Grundfrequenz bei f₀ ≈ 50,3 kHz wird durchgelassen.
- Das Ausgangssignal ist nahezu sinusförmig.





# Task 6 – Fourier-Analyse eines komplexen Filters

## 1. Ziel
Ziel dieser Aufgabe ist es, die Fourier-Zerlegung einer Rechteckschwingung mit dem Frequenzverhalten eines komplexen Bandpass-Filters zu verknüpfen.  
Untersucht wird, wie ein Filter mit mehreren Resonanzstellen aus einer Rechteckspannung einzelne Harmonische selektiv verstärkt und andere stark dämpft.

## 2. Theoretischer Hintergrund

Eine ideale Rechteckschwingung besteht aus:

- Grundfrequenz f₁  
- Ungeraden Harmonischen:  
  - 3. Harmonische: 3·f₁  
  - 5. Harmonische: 5·f₁  
  - 7. Harmonische: 7·f₁  
  - ...

Ein Filter mit einer ausgeprägten Resonanzfrequenz f₀ lässt nur Frequenzen in der Nähe von f₀ passieren und unterdrückt alle anderen.

## 3. Aufbau der Schaltung (nach Folie 15)

Bauteile:

| Bauteil | Wert |
|--------|------|
| Quelle | Rechteckspannung, 5 V |
| L1 | 10 µH |
| C1 | 1 nF |
| R1 | 25 Ω |
| C2 | 2 nF |
| L2 | 20 µH |
| R2 | 100 Ω |

Die Schaltung bildet eine T-Struktur aus zwei Schwingkreisen und einem Serienwiderstand.

## 4. Simulationen (GIFs)

### a) Grundfrequenz bei 1.2 MHz
![1.2 MHz](https://raw.githubusercontent.com/agshala/SV2/main/Task6_1.2MHz.gif)

### b) 3. Harmonische bei 3.5 MHz
![3.5 MHz](https://raw.githubusercontent.com/agshala/SV2/main/Task6_3.5MHz.gif)

### c) Resonanz bei 5.9 MHz
![5.9 MHz](https://raw.githubusercontent.com/agshala/SV2/main/Task6_5.9MHz.gif)

## 5. Beobachtungen

### Zeitbereich
- Eingang: Rechtecksignal mit steilen Flanken  
- Ausgang:
  - Bei 1.2 MHz: stark gedämpft
  - Bei 3.5 MHz: leicht verstärkt
  - Bei 5.9 MHz: nahezu sinusförmig mit maximaler Amplitude

### Frequenzbereich
- Eingangsspektrum:  
  - Linien bei f₁, 3f₁, 5f₁, 7f₁, ...
- Ausgangsspektrum:
  - Dominanter Peak bei der Resonanzfrequenz (~5.9 MHz)
  - Niedrige Frequenzen und höhere Harmonische stark gedämpft

## 6. Erklärung

Das Filter wirkt als selektiver Frequenzdetektor:

- Die Grundfrequenz der Rechteckwelle liegt weit außerhalb des Durchlassbereichs → wird unterdrückt.
- Die 3. Harmonische liegt näher am Durchlassbereich → teilweise sichtbar.
- Die 5. Harmonische liegt nahe der Resonanzfrequenz → maximale Verstärkung.

Durch die Filterung der Fourier-Komponenten bleibt am Ausgang nahezu nur diejenige Sinusschwingung übrig, deren Frequenz der Resonanzfrequenz des Filters entspricht.  

Das Rechtecksignal wird dadurch in eine nahezu reine Sinusschwingung transformiert – ein praktisches Beispiel für spektrale Filterung nach der Fourier-Theorie.
