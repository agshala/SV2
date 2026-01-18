# Task 5 – Filterung von Obertönen (Rechteck-zu-Sinus-Wandler)

## 1. Ziel  
Ziel dieser Aufgabe ist es, den Zusammenhang zwischen der Fourier-Analyse einer Rechteckschwingung und der Filterwirkung eines LC-Bandpassfilters zu verstehen.  
Eine Rechteckschwingung besteht aus einer Grundschwingung und ungeraden Oberschwingungen. Der Bandpass soll nur die Grundfrequenz durchlassen und die Obertöne unterdrücken, sodass am Ausgang eine sinusförmige Spannung entsteht.

---

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

---

## 3. Berechnung der Resonanzfrequenz

Thomsonsche Formel:

f₀ = 1 / (2π√(LC))

f₀ = 1 / (2π√(1·10⁻³ · 10·10⁻⁹))

f₀ ≈ 50,3 kHz

Die Rechteckquelle wird daher auf **50,3 kHz** eingestellt.

---

## 4. Simulation (GIF)

![Rechteck-zu-Sinus-Filterung](https://raw.githubusercontent.com/agshala/SV2/main/task5.gif)

Das GIF zeigt:
- das Rechtecksignal am Eingang
- das gefilterte Signal am Ausgang des LC-Bandpasses

---

## 5. Beobachtung

Am Eingang liegt eine Rechteckspannung mit steilen Flanken und vielen Oberwellen.  
Am Ausgang erscheint eine nahezu sinusförmige Spannung. Die hohen Frequenzanteile sind stark gedämpft, während die Grundfrequenz erhalten bleibt.

---

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

---

## 7. Ergebnis

Die Simulation bestätigt:

- Der LC-Bandpass filtert die Obertöne der Rechteckschwingung.
- Nur die Grundfrequenz bei f₀ ≈ 50,3 kHz wird durchgelassen.
- Das Ausgangssignal ist nahezu sinusförmig.
