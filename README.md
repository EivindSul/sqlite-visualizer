# sqlite-visualizer
Dette verktøyet har som formål å forenkle arbeidsflyten min når jeg
bruker sqlite3 sammen med en hvilken som helst editor i terminalen.

## Installasjon

## Hvordan bruke
Kjøres med 
```bash
sql-visualizer -d database.db -f FILENAME
```
eller
```bash
sql-visualizer -d database.db -q "QUERY;"
```
Der database.db er en sqlite-database, FILENAME er en fil, og "QUERY;"
er en SQL-spørring lukket inn i anførselstegn.

Resultatet blir returnert i stdout, slik at man kan pipe eller lagre det etter behov.

### Hvordan fungerer det?
Verktøyet kjører spørringen eller filen i sqlite3 gjennom
kommandolinjegrensesnittet i en egen prosess, som lagrer dataen i en pipe.

```bash
mkfifo sqlite-results
sqlite3 -csv database.db "QUERY;" > sqlite-results
```

CSV-dataen blir tolket av forelder-prosessen, som viser det i terminalen til brukeren.
Denne prosessen kan kjøre hvor man ønsker det, men kjøres best i en terminal multiplexer.
Dette kan være tmux, zellij, eller et neovim buffer.

For mitt bruk så vil jeg ha resultatet i neovim eller zellij, instrukser for
å sette det opp står nedenfor.

## Integrasjon med multiplexer
### Neovim

### Zellij

### Tmux

