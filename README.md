# Bonanno Consulting Website

Statische Website für Bonanno Consulting.

## GitHub Pages Deployment

Die Website ist für GitHub Pages vorbereitet.

1. Repository auf GitHub erstellen.
2. Diese Dateien in den Root des Repositorys pushen.
3. In GitHub unter `Settings > Pages` die Quelle auf den gewünschten Branch setzen, zum Beispiel `main` und `/root`.
4. Als Custom Domain `wint.global` eintragen.
5. `Enforce HTTPS` aktivieren, sobald GitHub das Zertifikat bereitgestellt hat.

Die Datei `CNAME` setzt die Custom Domain automatisch auf:

```txt
wint.global
```

## DNS für wint.global

Für die Apex-Domain `wint.global` beim DNS-Anbieter folgende GitHub-Pages-Records setzen:

```txt
A     @     185.199.108.153
A     @     185.199.109.153
A     @     185.199.110.153
A     @     185.199.111.153
AAAA  @     2606:50c0:8000::153
AAAA  @     2606:50c0:8001::153
AAAA  @     2606:50c0:8002::153
AAAA  @     2606:50c0:8003::153
```

Optional für `www.wint.global`:

```txt
CNAME  www  <github-user-or-org>.github.io
```

DNS-Änderungen können bis zu 24 Stunden dauern.
