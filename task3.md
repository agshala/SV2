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
