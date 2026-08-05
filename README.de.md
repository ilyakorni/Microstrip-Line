<p align="center">
  <a href="README.md">Русский</a> | <a href="README.en.md">English</a> | <b>Deutsch</b>
</p>

# Simulation und Berechnung einer Mikrostreifenleitung

Dieses Repository enthält die Ergebnisse des Entwurfs, der analytischen Berechnung und der elektromagnetischen 3D-Simulation einer Mikrostreifenleitung, die für eine Betriebsfrequenz von **1,015 GHz** optimiert ist.

Das Projekt umfasst die mathematische Synthese der Leitungsgeometrie für ein Standard-50-Ohm-System, die CAD-Modellierung und die Vollwellenanalyse der Anpassungseigenschaften mittels numerischer Simulation.

---

## Projektstruktur

* `/cad` — Dreidimensionale CAD-Modelle der Struktur in den Formaten SolidWorks (`.sldprt`) und neutral (`.step`).
* `/calculations` — Analytische Berechnungen der Leitungsparameter in Mathcad (`.xmcd`).
* `/simulation` — Elektromagnetisches Vollwellen-Simulationsprojekt in CST Studio Suite (`.cst`).
* `/docs/images` — Grafische Ergebnisse der Berechnungen und Frequenzgangdiagramme.

---

## Analytische Parameterberechnung

Die mathematische Berechnung der geometrischen Parameter wurde in Mathcad durchgeführt. Als Substrat wurde ein 1 mm dickes Dielektrikum mit einer relativen Permittivität von $\varepsilon = 3,38$ gewählt.

![Analytische Berechnung](docs/images/calc_microstrip_analytical.png)

### Technische Daten und berechnete Parameter:
* **Soll-Wellenwiderstand ($Z_B$):** 50 Ohm
* **Streifenbreite ($b$):** 4,098 mm
* **Grenzfrequenz der Mode höherer Ordnung ($F_{crit}$):** 82,15 GHz
* **Dämpfungskoeffizient ($\alpha$):** 0,345 dB/m

---

## 3D-Modell und Geometrie

Basierend auf den berechneten Abmessungen wurde eine gekoppelte Mikrostreifenstruktur auf einem dielektrischen Substrat mit Massefläche entworfen. Die Anregung des HF-Signals erfolgt über diskrete Tore (Discrete Ports).

![3D-Modell in CST](docs/images/simulation_3d_model.png)

---

## Ergebnisse der elektromagnetischen Simulation

Die Analyse des Frequenzgangs wurde im Bereich von 0,8–1,2 GHz durchgeführt. Die optimale Anpassungsfrequenz der Struktur liegt bei $f_0 = 1,015$ GHz.

### Schlüsselparameter bei 1,015 GHz:

| Parameter | Symbol | Wert | Beschreibung |
| :--- | :---: | :---: | :--- |
| Reflexionsfaktor | S11 | -28.86 dB | Geringer Reflexionspegel, der eine ordnungsgemäße Anpassung bestätigt. |
| VSWR | VSWR1 | 1.086 | Der Wert bleibt nahe eins über das gesamte Betriebsband. |
| Eingangsimpedanz | Z11 | 50.49 Ohm | Entspricht dem Standard-50-Ohm-System. |

---

## Frequenzgang-Analyse

<details open>
  <summary><b>1. Reflexionsfaktor (S11)</b></summary>
  <br>
  
  <img src="docs/images/simulation_s_parameters.png" alt="S-Parameter" width="100%"/>

  * **Analyse:** Bei 1,0136–1,015 GHz beträgt die Resonanztiefe -28,86 dB, was auf minimale Leistungsverluste durch Reflexion hinweist.
  * **Bandbreite:** Bei dem Standardniveau von -10 dB reicht die angepasste Bandbreite von ca. 0,97 GHz bis 1,06 GHz.
</details>

<details open>
  <summary><b>2. Spannungs-Stehwellenverhältnis (VSWR)</b></summary>
  <br>
  
  <img src="docs/images/simulation_vswr.png" alt="VSWR" width="100%"/>

  * **Analyse:** Bei der Betriebsfrequenz von 1,015 GHz beträgt das VSWR 1,086, was auf eine hohe Anpassungsqualität hinweist.
</details>

<details open>
  <summary><b>3. Eingangsimpedanz (Z11)</b></summary>
  <br>
  
  <img src="docs/images/simulation_z_parameters.png" alt="Eingangsimpedanz" width="100%"/>

  * **Analyse:** Der Betrag der Eingangsimpedanz bei 1,015 GHz beträgt 50,49 Ohm, was eine nahtlose Integration mit Standard-50-Ohm-Komponenten gewährleistet.
</details>

## Lizenz

Copyright (c) 2026 Ilya Kornilov

Diese Quelle beschreibt Open Hardware (offene Hardware) und ist unter der CERN-OHL-P v2 lizenziert. 
Sie dürfen diese Quelle unter den Bedingungen der CERN-OHL-P v2 (https://cern.ch/cern-ohl) 
weiterverbreiten, modifizieren und Produkte auf deren Grundlage herstellen.

Diese Quelle wird OHNE JEGLICHE AUSDRÜCKLICHE ODER STILLSCHWEIGENDE GEWÄHRLEISTUNG vertrieben, 
EINSCHLIESSLICH DER GEWÄHRLEISTUNG DER MARKTGÄNGIGKEIT, ZUFRIEDENSTELLENDEN QUALITÄT ODER EIGNUNG 
FÜR EINEN BESTIMMTEN ZWECK. Die geltenden Bedingungen entnehmen Sie bitte der CERN-OHL-P v2.