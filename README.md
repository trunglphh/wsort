# Übung2
## 2.2. Speicherverwaltung
malloc, calloc, realloc
## 2.3. Fehlerbehandlung
- exit(3p)
- Fehlermeldung:
    - errno: perror(3p): lesbare String ausgeben
    - fprintf(3p), stderr
## 2.4. Generisches Sortieren
`void qsort(void*base, size_t nel, size_t width, int(*compare)(const void*, const void*))`
## 2.5. Eingabe- Ausgabe
stdio.h
- fgets(3p): Liest 1 Zeile in String
- fgetc(3p): Liest 1 Zeiche aus stdin; return Zeichen(int)/EOF/Fehler
- fputs(3p): Schreibt 1 String in stdout/stderr (schneller als printf)
- printf(3p)
- ferror(3p): 1 bei Fehler
- perror(3p): Fehlermeldung (errno setzen)
- feof(3p): 1 bei EOF (errno setzen)
- fflush(3p): Ausgabepuffer sofort in stdout
- close(3p)/fclose(3p)
string.h
- `strchr(const char*str, int c)`: Sucht erste c in str; return NULL wenn nicht gefunden/ Zeifer auf c
- `strcmp(const char*s1,const char*s2)`: Vergleich 2 String alphabetisch; return s1-s2
- `strcpy(char*dest, const char*src)`:
  - Kopiert String von src nach dest, return Zeiger auf dest
  - Sicherer: `strncpy(ziel, quelle, sizeof(ziel-1)` 
## 2.6. valgrind: Debug
## wsort
  Liste von Wörten aus *stdin* einliest -> alphabet sortiert -> *stdout*
  - Einlesen, Ausgeben: jedes Wort in einer eigenen Zeile
  - Zeichen: char (1 Byte)
  - Wort durch *\n* getrennt; jede Zeile endet mit *\n* (letzte Zeile ist nicht zwangläufig)
  - 100 Zeichen überschreiten -> Fehlermeldung
  - Leere Zeile -> ignorieren
  - malloc, realloc
  -  Strg-D sendet EOF an die Anwendung und beendet somit die Eingabe
