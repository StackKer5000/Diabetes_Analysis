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

1) Risikofaktoren

Diabetes_Status, 
Bluthochdruck, 
Cholesterin_hoch,
Cholesterin_Check, 
BMI,
Raucher_Status,
Schlaganfall,
Herzerkrankung_Infarkt, 
Sportliche_Aktivitaet, 
Obst_Konsum,
Gemuese_Konsum,
Hoher_Alkoholkonsum, 
Krankenversicherung, 
Kein_Arzt_wegen_Kosten, 
Allgemeine_Gesundheit,
Psychische_Gesundheit, 
Koerperliche_Gesundheit, 
Einschränkung_Gehen, 
Geschlecht, 
Altersgruppe, 
Bildungsstand,
Einkommensstufe 


2) Altersgruppen:

Altersgruppe  Alter 
1       18 - 24 
2       25 - 29 
3     	30 - 34 
4     	35 - 39 
5     	40 - 44 
6     	45 - 49 
7    	50 - 54 
8     	55 - 59 
9     	60 - 64 
10      65 - 69 
11  	70 - 74 
12 	    75 - 79 
13  	80 oder älter 


3) BMI-Einteilung nach WHO:

BMI_Kategorie
Untergewicht             < 18.5
Normalgewicht            18.5 - 24.9
Übergewicht 	         25.0 - 29.9
Adipositas Grad I        30.0 - 34.9
Adipositas Grad II       35.0 - 39.9
Adipositas Grad III      >= 40.0


4) Bildung und Einkommen

Eingruppierung Bildung

1  -  Never attended school or only kindergarten
2  -  Grades 1 through 8 (Elementary)
3  -  Grades 9 through 11 (Some high school)
4  -  Grade 12 or GED (High school graduate)
5  -  College 1 year to 3 years (Some college or technical school)
6  -  College 4 years or more (College graduate)

Eingruppierung Haushaltseinkommen

1  -  Less than $10,000
2  -  Less than $15,000 ($10,000 to less than $15,000)
3  -  Less than $20,000 ($15,000 to less than $20,000)
4  -  Less than $25,000 ($20,000 to less than $25,000)
5  -  Less than $35,000 ($25,000 to less than $35,000)
6  -  Less than $50,000 ($35,000 to less than $50,000)
7  -  Less than $75,000 ($50,000 to less than $75,000)
8  -  $75,000 or more
