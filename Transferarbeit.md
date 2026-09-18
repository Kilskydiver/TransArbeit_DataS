# Schweizerische Fachschule TEKO
## Transferarbeit - Data Science

**Modul:** Data Science  
**Abgabe:** Fr. 18.09.26, 23:59 Uhr (IPYNB-Datei per E-Mail an den Dozenten)  
**Arbeitsform:** Einzelarbeit oder Gruppe (max. 2 Personen)  
**Hilfsmittel:** Open Book, KI-Tools erlaubt (Quellen müssen angegeben werden)  

---

## 1. Lernziele

Die Studierenden können nach Abschluss der Transferarbeit:
- einen realen Datensatz eigenständig importieren, analysieren und aufbereiten
- eine geeignete Machine-Learning-Aufgabenstellung aus den Daten ableiten (Use-Case-Analyse)
- relevante Features aus Rohdaten erstellen und auswählen
- ein geeignetes ML-Modell wählen, trainieren und evaluieren
- die Ergebnisse kritisch beurteilen und Verbesserungspotenzial benennen
- ihre Arbeit vor der Klasse präsentieren und Fragen beantworten

---

## 2. Datensatz

### E-Commerce Shipping Dataset
- **Quelle:** Kaggle E-Commerce Shipping Dataset
- **Umfang:** ~11 000 Bestellungen, 12 Spalten
- **Mögliche Zielvariable:** `Reached.on.Time_Y.N` (Lieferung pünktlich: Ja/Nein)
- **Beschreibung:** Ein internationaler E-Commerce-Händler erfasst Bestelldaten inklusive Produktgewicht, Versandart, Kundenbewertungen und ob die Lieferung pünktlich ankam. Das Modell soll vorhersagen, ob eine neue Bestellung rechtzeitig beim Kunden ankommt.

- **Pfad:** ./ressourcen/Train.csv
---

## 3. Aufgabenstellung

Die Arbeit gliedert sich in fünf Pflichtteile. Jeder Teil ist im Jupyter Notebook zu dokumentieren (Markdown-Zellen für Erklärungen, Code-Zellen für Implementierung).

### Teil 1 - Use-Case-Analyse (ca. 1 Seite)
Beantworten Sie folgende Fragen schriftlich im Notebook:
1. **Datensatz-Beschreibung:** Was wurde erfasst, von wem und warum?
2. **Business-Fragestellung:** Welches konkrete Problem soll das Modell lösen? Formulieren Sie die Fragestellung in einem Satz (z.B. "Kann anhand von Bestellmerkmalen vorhergesagt werden, ob eine Lieferung pünktlich ankommt?").
3. **Art des Problems:** Handelt es sich um Klassifikation, Regression oder Clustering? Begründen Sie die Wahl.
4. **Mehrwert:** Welchen Nutzen hätte das trainierte Modell für ein Unternehmen?
5. **Einschränkungen:** Welche Risiken, ethischen Fragen oder Grenzen sehen Sie beim Einsatz eines solchen Modells?

### Teil 2 - Datenprozessierung (Code + Erklärungen)
Führen Sie folgende Schritte durch und dokumentieren Sie jeden Schritt mit einer kurzen Erklärung:

**2.1 Import und erster Überblick**
- Datensatz laden (`pd.read_csv()` oder äquivalent)
- Form, Datentypen und erste Zeilen ausgeben (`shape`, `info()`, `head()`)
- Statistische Kennzahlen berechnen (`.describe()`)

**2.2 Datenqualität prüfen und bereinigen**
- Fehlende Werte identifizieren und behandeln (Strategie begründen)
- Dubletten erkennen und entfernen
- Ausreisser analysieren (IQR-Methode oder Z-Score) und Entscheidung dokumentieren
- Zeichenfehler und inkonsistente Werte korrigieren

**2.3 Explorative Datenanalyse (EDA)**
- Mindestens 3 Visualisierungen mit Interpretation:
  - Verteilung der Zielvariable
  - Korrelationen oder Zusammenhänge zwischen Merkmalen
  - Eine weitere frei gewählte, inhaltlich begründete Darstellung
- Erkenntnisse aus der EDA in eigenen Worten zusammenfassen

**2.4 Feature Engineering**
- Mindestens 2 neue Features erstellen oder transformieren, z.B.:
  - Kategorische Variablen codieren (One-Hot-Encoding, Label-Encoding)
  - Datumsspalten in sinnvolle numerische Features umwandeln (z.B. Wochentag, Monat)
  - Verhältnisse oder Differenzen berechnen (z.B. Umsatz pro Einheit)
  - Textlängen, Binning, Log-Transformation, etc.
- Jedes neue Feature kurz begründen

**2.5 Train/Test-Split**
- Daten in Trainings- und Testset aufteilen (`train_test_split`)
- Verhältnis und ggf. Stratifizierung begründen

### Teil 3 - Modellwahl und Training (Code + Erklärungen)

**3.1 Modellwahl**
- Wählen Sie 2 verschiedene Modelle und begründen Sie die Auswahl kurz (z.B. Logistic Regression, Decision Tree, Random Forest, KNN, XGBoost, K-Means, ...)
- Erklären Sie in 2-3 Sätzen, wie das Modell funktioniert (keine mathematische Herleitung nötig)

**3.2 Training**
- Trainieren Sie jedes Modell auf den Trainingsdaten
- Nutzen Sie ggf. Hyperparameter-Tuning (Grid Search oder manuelle Anpassung) - dokumentieren Sie, was Sie verändert haben und warum

**3.3 Vorhersage**
- Erstellen Sie Vorhersagen auf dem Testset
- Geben Sie die Vorhersagen übersichtlich aus

### Teil 4 - Auswertung, Fazit und Verbesserungsmöglichkeiten

**4.1 Modell-Evaluation**
Wählen Sie die passenden Metriken für Ihr Problem und berechnen Sie diese:

| Aufgabentyp | Mindest-Metriken |
|---|---|
| Klassifikation | Accuracy, Precision, Recall, F1-Score, Confusion Matrix |
| Regression | MAE, RMSE, $R^2$ |
| Clustering | Silhouette Score, Elbow-Methode |

Vergleichen Sie die Ergebnisse Ihrer 2 Modelle in einer übersichtlichen Tabelle.

**4.2 Interpretation**
- Was sagen die Metriken aus? Ist das Modell gut genug für den Praxiseinsatz?
- Welches Modell schneidet besser ab und warum?
- Welche Features sind am wichtigsten? (Feature Importance, falls verfügbar)

**4.3 Fazit**
- Beantworten Sie die in Teil 1 formulierte Business-Fragestellung
- Wurde das Ziel erreicht?

**4.4 Verbesserungsmöglichkeiten**
- Nennen Sie mindestens 3 konkrete Verbesserungsmöglichkeiten, z.B.:
  - Mehr oder bessere Daten
  - Weitere Features
  - Andere Modelle oder Hyperparameter
  - Andere Vorverarbeitungsstrategien

### Teil 5 - Präsentation des Modells
Die Präsentation findet am letzten Kurstag statt.
- **Dauer:** ca. 10 Minuten Präsentation + 5 Minuten Fragen
- **Format:** Folien (PowerPoint, PDF) oder direkt aus dem Notebook
- **Inhalt (Pflicht):**
  1. Datensatz und Business-Fragestellung
  2. Wichtigste Erkenntnisse aus der EDA - mindestens 1 Visualisierung zeigen
  3. Modellwahl und Ergebnisse - Metriken erklären
  4. Fazit und Verbesserungsmöglichkeiten

Bei Gruppenarbeiten müssen beide Mitglieder aktiv sprechen.

---

## 4. Abgabe-Anforderungen

| Artefakt | Beschreibung |
|---|---|
| `Transferarbeit_[Name].ipynb` | Jupyter Notebook mit vollständigem, ausführbarem Code und Dokumentation |
| Originaldatensatz (CSV) | Als Anhang oder Link zum Download im Notebook angegeben |

Das Notebook muss vollständig ausführbar sein (Kernel Restart & Run All ohne Fehler).

**Benennung der Datei:**
- Einzelarbeit: `DSC_TA_Nachname_Vorname.ipynb`
- Gruppenarbeit: `DSC_TA_Nachname1_Nachname2.ipynb`

Abgabe per E-Mail an den Dozenten bis Fr. 18.09.26, 23:59 Uhr.

---

## 5. Bewertungsraster

Die Transferarbeit wird mit 100 Punkten bewertet. Die Note ergibt sich gemäss TEKO-Notenskala.

| Bereich | Punkte | Anteil |
|---|---|---|
| Jupyter Notebook (Teile 1-4) | 60 Punkte | 60% |
| Präsentation (Teil 5) | 40 Punkte | 40% |
| **Total** | **100 Punkte** | **100%** |

Die Note berechnet sich somit als:
$$\text{Note} = \left(\frac{5}{100}\right) \times \text{Punktezahl} + 1$$

### Bewertung Jupyter Notebook (60 Punkte)

**Teil 1 - Use-Case-Analyse (8 Punkte)**

| Kriterium | 0 Punkte | 1-2 Punkte | 3 Punkte | 4 Punkte |
|---|---|---|---|---|
| **Business-Fragestellung** (4 Pt.) | Nicht vorhanden | Vage oder unvollständig | Klar formuliert, aber ohne Bezug zu Nutzen | Präzise, mit konkretem Mehrwert für ein Unternehmen |
| **Problemtyp & Limitationen** (4 Pt.) | Nicht vorhanden | Nur einer der Aspekte bearbeitet | Problemtyp korrekt + Einschränkungen oberflächlich | Beides korrekt, mit eigenständiger Reflexion zu Risiken |

**Teil 2 - Datenprozessierung (22 Punkte)**

| Kriterium | 0 Punkte | 1-3 Punkte | 4-6 Punkte | 7-8 Punkte |
|---|---|---|---|---|
| **Import & Überblick** (8 Pt.) | Kein Import oder Fehler | Datensatz geladen, kaum Analyse | `shape`, `info`, `describe` vorhanden | Vollständiger Überblick mit sinnvollen Beobachtungen im Text |
| **Bereinigung** (7 Pt.) | Keine Bereinigung | NaN oder Dubletten, aber ohne Begründung | Mehrere Schritte mit teilweiser Begründung | Alle relevanten Schritte mit nachvollziehbarer, schriftlicher Begründung |
| **EDA & Feature Engineering** (7 Pt.) | Fehlend | 1 Plot, kein FE oder umgekehrt | 2 Plots + 1 Feature, oberflächliche Erklärung | $\ge 3$ Plots mit Interpretation + $\ge 2$ sinnvolle Features begründet |

**Teil 3 - Modellwahl und Training (15 Punkte)**

| Kriterium | 0 Punkte | 1-3 Punkte | 4-6 Punkte | 7-8 Punkte |
|---|---|---|---|---|
| **Modellwahl & Begründung** (8 Pt.) | Kein Modell oder falscher Typ | 1 Modell ohne Begründung | 2 Modelle, Begründung teilweise | 2+ Modelle mit klarer Begründung und kurzer Funktionserklärung |
| **Training & Tuning** (7 Pt.) | Code fehlt oder läuft nicht | Modell trainiert, kein Tuning | Training korrekt, 1 Hyperparameter angepasst | Training korrekt + dokumentiertes Tuning mit Vergleich |

**Teil 4 - Auswertung & Fazit (15 Punkte)**

| Kriterium | 0 Punkte | 1-3 Punkte | 4-6 Punkte | 7-8 Punkte |
|---|---|---|---|---|
| **Metriken & Vergleich** (8 Pt.) | Keine Metriken | Eine Metrik, kein Modellvergleich | Passende Metriken, Modelle verglichen | Alle passenden Metriken, übersichtlicher Vergleich + Interpretation |
| **Fazit & Verbesserungen** (7 Pt.) | Fehlend | Fazit vorhanden, keine Verbesserungen | Beides vorhanden, aber oberflächlich | Business-Frage klar beantwortet + $\ge 3$ konkrete, begründete Verbesserungen |

### Bewertung Präsentation (40 Punkte)

| Kriterium | 0 Punkte | 1-8 Punkte | 9-14 Punkte | 15-20 Punkte |
|---|---|---|---|---|
| **Inhalt & Vollständigkeit** (20 Pt.) | Kaum Inhalte | 1-2 Pflichtteile fehlen | Alle Teile vorhanden, aber lückenhaft | Alle Pflichtteile klar, vollständig und strukturiert dargestellt |
| **Verständlichkeit & Fachkompetenz** (20 Pt.) | Inhalte nicht verständlich | Erklärungen teilweise korrekt, kaum Fachbegriffe | Verständlich erklärt, Fachbegriffe mehrheitlich korrekt | Souverän erklärt, Fachbegriffe korrekt, Fragen kompetent beantwortet |

---

## 6. Hinweise und Empfehlungen
- Fangen Sie früh an. Die Datenprozessierung braucht oft mehr Zeit als erwartet.
- Dokumentieren Sie laufend. Ein Notebook ohne Erklärungen in Markdown-Zellen wird nicht vollständig bewertet.
- Visualisierungen beschriften. Jeder Plot braucht Titel, Achsenbeschriftungen und eine Interpretation im Text.
- **KI-Tools:** Sie dürfen Tools wie ChatGPT oder GitHub Copilot nutzen. Fügen Sie am Ende des Notebooks einen kurzen Abschnitt ein, der beschreibt, wofür Sie KI verwendet haben.
- Code muss laufen. Kommentieren Sie keine Fehler weg - beseitigen Sie sie.
- Bei Fragen: Teams-Chat oder nächste Vorlesung nutzen.

---
*Data Science - TEKO Luzern | Dozent: Markus Kessler | Version 1.1 | Juni 2026*