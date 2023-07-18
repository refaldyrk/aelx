# AELX

AELX ist eine Befehlszeilensoftware, mit der Sie `.aelx`-Konfigurationsdateien lesen und verarbeiten können. Diese Software unterstützt das Extrahieren von Schlüssel-Wert-Paaren aus der Konfigurationsdatei und bietet Optionen zum Ausgeben der Daten im JSON-Format oder als Umgebungsvariablen.

## Installation

Um AELX zu installieren, befolgen Sie diese Schritte:

1. Klonen Sie das AELX-Repository:

   ```shell
   git clone https://github.com/refaldyrk/aelx.git
   ```

2. Wechseln Sie in das Projektverzeichnis:

   ```shell
   cd aelx
   ```

3. Führen Sie AELX aus:

   ```shell
   aelx --f=something.aelx -k=key
   ```

## Verwendung

Führen Sie den Befehl `aelx` mit den folgenden Optionen aus:

- `-k`: Der Schlüssel, dessen Wert Sie aus der Konfigurationsdatei abrufen möchten.
- `--f`: Der Name der `.aelx`-Datei, die Sie lesen möchten.
- `-j`: Optionale Flagge zum Ausgeben der Daten im JSON-Format. Standard: `false`.
- `--o`: Optionale Flagge zum Festlegen des Ausgabedateinamens im JSON-Format. Standard: `aelx.json`.
- `-e`: Optionale Flagge zum Ausgeben der Daten als Umgebungsvariablen. Standard: `false`.

### Beispielanwendung

1. Abrufen des Werts eines bestimmten Schlüssels aus der Konfigurationsdatei:

   ```shell
   aelx -k <Schlüsselname> --f <Dateiname.aelx>
   ```

   Beispiel:
   ```shell
   aelx -k hello --f config.aelx
   ```

2. Ausgabe der Daten im JSON-Format:

   ```shell
   aelx -k <Schlüsselname> --f <Dateiname.aelx> -j true
   ```

   Beispiel:
   ```shell
   aelx -k hello --f config.aelx -j true
   ```

3. Ausgabe der Daten im JSON-Format mit einem benutzerdefinierten Dateinamen:

   ```shell
   aelx -k <Schlüsselname> --f <Dateiname.aelx> -j true --o <ausgabe.json>
   ```

   Beispiel:
   ```shell
   aelx -k hello --f config.aelx -j true --o output.json
   ```

4. Ausgabe der Daten als Umgebungsvariablen:

   ```shell
   aelx -k <Schlüsselname> --f <Dateiname.aelx> -e true
   ```

   Beispiel:
   ```shell
   aelx -k hello --f config.aelx -e true
   ```

## `.aelx`-Dateiformat

Die `.aelx`-Datei verwendet ein spezifisches Format. Hier ist ein Beispiel für das unterstützte `.aelx`-Dateiformat:

```
project: start|
[Schlüssel-1] Wert-1|
[Schlüssel-2] Wert-2|
[Schlüssel-3] Wert-3|
project: end|
```

Stellen Sie sicher, dass Ihre `.aelx`-Datei diesem Format entspricht, um eine korrekte Datenextraktion sicherzustellen.

## Beispiel für eine `.aelx`-Konfigurationsdatei

Hier ist ein Beispielinhalt einer `.aelx`-Konfigurationsdatei:

```
project: start|
hello[welt]|
lorem[ipsum]|
project: end|
```

In diesem Beispiel gibt es zwei Schlüssel-Wert-Paare:

- Schlüssel: `hello`, Wert: `welt`
- Schlüssel: `lorem`, Wert: `ipsum`

Sie können den `aelx`-Befehl verwenden, um die Werte dieser Schlüssel abzurufen oder entsprechend Ihren Anforderungen Datenextraktionen durchzuführen.