# AELX

AELX is een command-line software waarmee je `.aelx` configuratiebestanden kunt lezen en verwerken. Deze software ondersteunt het extraheren van sleutel-waardeparen uit het configuratiebestand en biedt opties om de gegevens uit te voeren in JSON-formaat of als omgevingsvariabelen.

## Installatie

Om AELX te installeren, volg je deze stappen:

1. Clone de AELX repository:

   ```shell
   git clone https://github.com/refaldyrk/aelx.git
   ```

2. Ga naar de projectmap:

   ```shell
   cd aelx
   ```

3. Voer AELX uit:

   ```shell
   aelx --f=something.aelx -k=key
   ```

## Gebruik

Voer het `aelx` commando uit met de volgende opties:

- `-k`: De sleutel waarvan je de waarde uit het configuratiebestand wilt halen.
- `--f`: De naam van het `.aelx` bestand dat je wilt lezen.
- `-j`: Optionele vlag om de gegevens in JSON-formaat uit te voeren. Standaard: `false`.
- `--o`: Optionele vlag om de uitvoer naar een JSON-bestand te sturen. Standaard: `aelx.json`.
- `-e`: Optionele vlag om de gegevens als omgevingsvariabelen uit te voeren. Standaard: `false`.

### Voorbeeldgebruik

1. Haal de waarde van een specifieke sleutel op uit het configuratiebestand:

   ```shell
   aelx -k <sleutel-naam> --f <bestandsnaam.aelx>
   ```

   Voorbeeld:
   ```shell
   aelx -k hello --f config.aelx
   ```

2. Voer de gegevens uit in JSON-formaat:

   ```shell
   aelx -k <sleutel-naam> --f <bestandsnaam.aelx> -j true
   ```

   Voorbeeld:
   ```shell
   aelx -k hello --f config.aelx -j true
   ```

3. Voer de gegevens uit in JSON-formaat met een aangepaste bestandsnaam:

   ```shell
   aelx -k <sleutel-naam> --f <bestandsnaam.aelx> -j true --o <output.json>
   ```

   Voorbeeld:
   ```shell
   aelx -k hello --f config.aelx -j true --o output.json
   ```

4. Voer de gegevens uit als omgevingsvariabelen:

   ```shell
   aelx -k <sleutel-naam> --f <bestandsnaam.aelx> -e true
   ```

   Voorbeeld:
   ```shell
   aelx -k hello --f config.aelx -e true
   ```

## `.aelx` Bestandsformaat

Het `.aelx` bestand gebruikt een specifiek formaat. Hier is een voorbeeld van het ondersteunde `.aelx` bestandsformaat:

```
project: start|
[sleutel-1] waarde-1|
[sleutel-2] waarde-2|
[sleutel-3] waarde-3|
project: end|
```

Zorg ervoor dat jouw `.aelx` bestand dit formaat volgt om ervoor te zorgen dat de gegevens correct worden geëxtraheerd.

## Voorbeeld `.aelx` Configuratiebestand

Hier is een voorbeeld van de inhoud van een `.aelx` configuratiebestand:

```
project: start|
hello[wereld]|
lorem[ipsum]|
project: end|
```

In dit voorbeeld zijn er twee sleutel-waardeparen:

- Sleutel: `hello`, Waarde: `wereld`
- Sleutel: `lorem`, Waarde: `ipsum`

Je kunt het `aelx` commando gebruiken om de waarden van deze sleutels op te halen of om gegevens te extraheren zoals je dat nodig hebt.