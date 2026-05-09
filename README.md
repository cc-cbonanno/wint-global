# Bonanno Consulting Website

Statische Website für Bonanno Consulting.

## GitHub Pages Deployment

Die Website ist für GitHub Pages vorbereitet.

1. Repository auf GitHub erstellen.
2. Diese Dateien in den Root des Repositorys pushen.
3. In GitHub unter `Settings > Pages` die Quelle auf den gewünschten Branch setzen, zum Beispiel `main` und `/root`.
4. Keine Custom Domain eintragen, wenn `bonanno-consulting.com` beim Hoster per Weiterleitung läuft.

Die GitHub-Pages-Ziel-URL lautet:

```txt
https://cc-cbonanno.github.io/wint-global/
```

## Weiterleitung von bonanno-consulting.com

Beim Hoster für `bonanno-consulting.com` eine permanente Weiterleitung einrichten:

```txt
Quelle: bonanno-consulting.com
Ziel:   https://cc-cbonanno.github.io/wint-global/
Typ:    301 permanent
```

Konfigurationsbeispiele liegen im Ordner `redirect/`.
