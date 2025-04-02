# 📊 Verkaufsstatistik nach Ländern (ABAP-Projekt)

## 🧾 Beschreibung

Dieses ABAP-Projekt simuliert ein Szenario, bei dem Verkaufsdaten pro Land ausgewertet und analysiert werden. Die Daten befinden sich in einer internen Tabelle und stammen aus einer simulierten Datenquelle (z. B. einer Datenbanktabelle). Ziel ist es, aus diesen Daten nützliche Statistiken zu generieren.

---

## 🛠️ Bestandteile des Programms

### 1. Datenmodell
- `ty_sales`: Struktur für einzelne Verkaufsdatensätze (`country`, `revenue`)
- `lt_sales`: Interne Tabelle mit allen Verkaufsdatensätzen
- `ty_summary`: Struktur für aggregierte Statistikdaten pro Land (`country`, `total_revenue`, `order_count`)
- `lt_summary`: Hashed Table zur Speicherung der Zusammenfassung, basierend auf dem Land

---

### 2. Datenbefüllung
- Eine lokale Klasse `lcl_sales` beinhaltet eine `fill`-Methode, die Testdaten in die interne Tabelle `lt_sales` schreibt.
- Die `get_sales`-Methode gibt die Daten an den Hauptprogrammteil zurück.

---

### 3. Aggregation mittels `COLLECT`
- Mit Hilfe des `COLLECT`-Statements werden die Umsätze und Bestellmengen pro Land automatisch aufsummiert.
- Die Anzahl der Bestellungen wird durch `order_count = 1` realisiert.

---

### 4. Statistikberechnung
- Berechnung des **Gesamtumsatzes** pro Land
- Berechnung der **Anzahl der Bestellungen** pro Land
- Berechnung des **durchschnittlichen Umsatzes** (total_revenue / order_count)
- Ermittlung des Landes mit dem **höchsten durchschnittlichen Umsatz**
- Ermittlung des Landes mit der **höchsten Bestellanzahl**

---

## Ausgabe

Die Ergebnisse werden über `WRITE` auf dem Bildschirm ausgegeben.  
Es werden für jedes Land folgende Daten angezeigt:

- Land (Country)
- Gesamtumsatz
- Anzahl der Bestellungen
- Durchschnittlicher Umsatz

Zusätzlich werden die Länder mit dem höchsten Umsatz / Bestellungen hervorgehoben.

---

##  Lernziele & Fokus

- Anwendung von internen Tabellen und Strukturen
- Aggregation mit `COLLECT`
- Klassendefinition mit Methoden zur Datenbereitstellung
- Einfache statistische Auswertungen in ABAP
- Dynamische Auswertung mit nur einer Schleife

---

