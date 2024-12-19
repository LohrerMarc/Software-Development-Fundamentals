# Schritt-für-Schritt-Anleitung zur Normalisierung einer Datenbank-Struktur

## Einleitung
Die Normalisierung ist ein Prozess, der dabei hilft, Redundanzen und Anomalien in einer Datenbank zu vermeiden. Durch die Normalisierung wird die Datenbank in mehrere Tabellen aufgeteilt, um die Daten konsistenter und effizienter zu speichern.

In diesem Beispiel werden wir die Normalisierung anhand einer einfachen Datenbankstruktur für eine Schule Schritt für Schritt erklären.

## Ausgangssituation
Stellen wir uns vor, wir haben eine Tabelle, die Informationen über Schüler und ihre Kurse enthält:

| Schüler_ID | Schüler_Name | Kurs_ID | Kurs_Name  | Lehrer_ID | Lehrer_Name |
|:----------:|:------------:|:-------:|:----------:|:---------:|:-----------:|
| 1          | Max Mustermann | 101     | Mathematik | 201       | Herr Schmidt|
| 2          | Julia Müller   | 102     | Biologie   | 202       | Frau Meyer  |
| 1          | Max Mustermann | 102     | Biologie   | 202       | Frau Meyer  |

Diese Tabelle enthält redundante Daten, da Schüler- und Lehrerdaten mehrmals wiederholt werden.

## 1. Normalform (1NF)
Eine Tabelle befindet sich in der 1. Normalform, wenn:
- Alle Attributwerte atomar (unteilbar) sind.
- Es keine wiederholten Gruppierungen oder Arrays gibt.

Die Ausgangstabelle erfüllt bereits diese Anforderungen.

## 2. Normalform (2NF)
Eine Tabelle befindet sich in der 2. Normalform, wenn:
- Sie sich bereits in der 1. Normalform befindet.
- Alle Nicht-Schlüsselattribute vollständig vom Primärschlüssel abhängen.

Um die 2. Normalform zu erreichen, müssen wir die Tabelle in zwei Tabellen aufteilen: eine für die Schüler und eine für die Kurse.

### Schüler Tabelle

| Schüler_ID | Schüler_Name  |
|:----------:|:-------------:|
| 1          | Max Mustermann|
| 2          | Julia Müller  |

### Kurs Tabelle

| Kurs_ID | Kurs_Name  | Lehrer_ID |
|:-------:|:----------:|:---------:|
| 101     | Mathematik | 201       |
| 102     | Biologie   | 202       |

### Lehrer Tabelle

| Lehrer_ID | Lehrer_Name  |
|:---------:|:------------:|
| 201       | Herr Schmidt |
| 202       | Frau Meyer   |

### Schüler_Kurs Tabelle (Beziehungstabelle)

| Schüler_ID | Kurs_ID |
|:----------:|:-------:|
| 1          | 101     |
| 2          | 102     |
| 1          | 102     |

## 3. Normalform (3NF)
Eine Tabelle befindet sich in der 3. Normalform, wenn:
- Sie sich bereits in der 2. Normalform befindet.
- Kein Nicht-Schlüsselattribut transitiv vom Primärschlüssel abhängig ist.

Unsere Tabellen erfüllen bereits die Anforderungen der 3. Normalform, da alle Nicht-Schlüsselattribute direkt vom Primärschlüssel abhängen.

## Zusammenfassung
Durch die Normalisierung haben wir die Ausgangstabelle in mehrere Tabellen aufgeteilt, um Redundanzen zu vermeiden und die Datenkonsistenz zu erhöhen. Hier ist die finale Struktur:

### Schüler Tabelle

| Schüler_ID | Schüler_Name  |
|:----------:|:-------------:|
| 1          | Max Mustermann|
| 2          | Julia Müller  |

### Kurs Tabelle

| Kurs_ID | Kurs_Name  | Lehrer_ID |
|:-------:|:----------:|:---------:|
| 101     | Mathematik | 201       |
| 102     | Biologie   | 202       |

### Lehrer Tabelle

| Lehrer_ID | Lehrer_Name  |
|:---------:|:------------:|
| 201       | Herr Schmidt |
| 202       | Frau Meyer   |

### Schüler_Kurs Tabelle (Beziehungstabelle)

| Schüler_ID | Kurs_ID |
|:----------:|:-------:|
| 1          | 101     |
| 2          | 102     |
| 1          | 102     |

Durch diese Schritte haben wir eine normalisierte Datenbankstruktur erstellt, die effizienter und konsistenter ist.
