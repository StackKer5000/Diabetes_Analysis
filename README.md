## Explorative Datenanalyse von Diabetes-Risikofaktoren

Dieses GitHub-Projekt enthält die statistische Auswertung und Modellierung von Einflussgrößen auf den Diabetes-Status. Die Analyse basiert auf den Großbefragungsdaten des Behavioral Risk Factor Surveillance System (BRFSS) der US-amerikanischen Gesundheitsbehörde CDC. Ziel der Untersuchung ist die Identifikation unbereinigter Zusammenhänge im Vergleich zu den echten, bereinigten Hebelwirkungen in einem multivariaten Gesamtmodell.

## Projektstruktur

- data/data_in_use/ : Ordner für den Datensatz diabetes_binary_health_indicators_BRFSS2015.csv
- Jupyter Notebook mit dem dokumentierten Python-Code
- BMI_Effekt_Tabelle.pptx : Die PowerPoint-Präsentation zum Projekt
- README.md : Projektdokumentation

## Verwendete Python-Bibliotheken

- Pandas: Datenbereinigung, Transformation und Kreuztabellen
- NumPy: Mathematische Berechnungen und Exponential-Transformationen
- Seaborn: Datenvisualisierungen mit barplot, lineplot und heatmap unter Nutzung des colorblind-Farbschemas
- Matplotlib: Grafikanpassungen, Achsen-Styling und Platzierung der Textbeschriftungen
- Statsmodels: Berechnung des Logit-Modells für die logistische Regression

## Wesentliche Projektschritte

1. Datenaufbereitung: Laden der 253.680 Beobachtungen, Übersetzung der englischen Rohvariablen ins Deutsche und Speicheroptimierung durch Konvertierung in speicherschonende Ganzzahl-Datentypen (int8).
2. Feature Engineering: Einteilung des Body-Mass-Index (BMI) in die offiziellen WHO-Gewichtsklassen sowie Erstellung numerischer Kategorien-Kodes für die Korrelationsanalyse.
3. Explorative Analyse: Durchführung direkter Gruppenvergleiche zur Ermittlung unbereinigter Diabetes-Raten nach Geschlecht, Altersstufen, Vorerkrankungen, sozialem Status und subjektiven Gesundheitstagen.
4. Multivariate Modellierung: Berechnung einer logistischen Regression zur Isolierung der tatsächlichen, bereinigten Odds Ratios (OR) inklusive 95-Prozent-Konfidenzintervallen.

## Kern-Erkenntnisse

Das Regressionsmodell erzielt eine Erklärungsgüte von 20,15 Prozent (Pseudo-R-Quadrat).
- Medizinische Haupttreiber: Bluthochdruck (OR: 2,19) und hohes Cholesterin (OR: 1,83) dominieren das bereinigte Erkrankungsrisiko im Gesamtmodell.
- Kumulativer BMI-Effekt: Ein einzelner BMI-Punkt steigert das Risiko kontinuierlich um 6,5 Prozent (OR: 1,065). Dieser Effekt addiert sich bei einer Gewichtserhöhung um 10 BMI-Punkte auf einen Gesamtrisiko-Anstieg von knapp 88 Prozent.
- Sozioökonomische Verzerrung aufgelöst: Niedrige Bildung und geringes Einkommen zeigen im paarweisen Vergleich extreme Diabetes-Raten von fast 25 Prozent. Nach der Bereinigung um Alter und Gewicht im Gesamtmodell kehren sich beide Parameter in echte Schutzfaktoren um (OR unter 1,0). Dies beweist, dass ein geringer sozialer Status keine biologische Ursache für Diabetes ist, sondern statistisch primär mit einem höheren Lebensalter und Gewicht einhergeht.
- Statistische Absicherung: Sämtliche untersuchten Prädaktoren sind hochgradig signifikant, da kein Konfidenzintervall die Neutrallinie von 1,0 schneidet oder berührt.

## Referenzen

- Datenquelle CDC: Centers for Disease Control and Prevention (CDC), Behavioral Risk Factor Surveillance System (BRFSS 2015).
- Daten-Repository: Kaggle Diabetes Health Indicators Dataset von Alex Teboul.
- Medizinischer Standard: Weltgesundheitsorganisation (WHO) Richtlinie zur Einteilung der BMI-Gewichtsklassen.

## Benutzte Einteilungen aus dem Dataset Notebook

1. Risikofaktoren<br>
Diabetes_Status,<br>
 Bluthochdruck,<br>
 Cholesterin_hoch,<br>
 Cholesterin_Check,<br>
 BMI,<br> 
 Raucher_Status,<br> 
 Schlaganfall,<br> 
 Herzerkrankung_Infarkt,<br> 
 Sportliche_Aktivitaet,<br> 
 Obst_Konsum,<br> 
 Gemuese_Konsum,<br> 
 Hoher_Alkoholkonsum,<br> 
 Krankenversicherung,<br> 
 Kein_Arzt_wegen_Kosten,<br> 
 Allgemeine_Gesundheit,<br> 
 Psychische_Gesundheit,<br> 
 Koerperliche_Gesundheit,<br> 
 Einschraenkung_Gehen,<br> 
 Geschlecht,<br> 
 Altersgruppe,<br> 
 Bildungsstand, <br>
 Einkommensstufe<br>
<br>
<br>
2. Altersgruppen:<br>

Altersgruppe Alter 1: 18 - 24<br>
2: 25 - 29<br>
3: 30 - 34<br>
4: 35 - 39<br>
5: 40 - 44<br>
6: 45 - 49<br>
7: 50 - 54<br>
8: 55 - 59<br>
9: 60 - 64<br>
10: 65 - 69<br>
11: 70 - 74<br>
12: 75 - 79<br>
13: 80 oder aelter<br>
<br>
<br>
3. BMI-Einteilung nach WHO:<br>

BMI_Kategorie Untergewicht < 18.5<br>
Normalgewicht 18.5 - 24.9<br>
Uebergewicht 25.0 - 29.9<br>
Adipositas Grad I 30.0 - 34.9<br>
Adipositas Grad II 35.0 - 39.9<br>
Adipositas Grad III >= 40.0<br>
<br>
<br>
4. Bildung und Einkommen<br>

Eingruppierung Bildung<br>
1 - Never attended school or only kindergarten<br>
2 - Grades 1 through 8 (Elementary)<br>
3 - Grades 9 through 11 (Some high school)<br>
4 - Grade 12 or GED (High school graduate)<br>
5 - College 1 year to 3 years (Some college or technical school)<br>
6 - College 4 years or more (College graduate)<br>
<br>
Eingruppierung Haushaltseinkommen<br>
1 - Less than $10,000<br>
2 - Less than $15,000 ($10,000 to less than $15,000)<br>
3 - Less than $20,000 ($15,000 to less than $20,000)<br>
4 - Less than $25,000 ($20,000 to less than $25,000)<br>
5 - Less than $35,000 ($25,000 to less than $35,000)<br>
6 - Less than $50,000 ($35,000 to less than $50,000)<br>
7 - Less than $75,000 ($50,000 to less than $75,000)<br>
8 - $75,000 or more
