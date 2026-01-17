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
