# Deployment: GitHub Pages + bonanno-consulting.com

Diese Website ist statisch und kann direkt über GitHub Pages gehostet werden.

## 1. GitHub Repository erstellen

1. Auf GitHub ein neues Repository erstellen, zum Beispiel:
   `wint-global`
2. Repository zunächst leer lassen.
3. Keine README, keine `.gitignore`, keine Lizenz auf GitHub erzeugen.

## GitHub CLI Login

Die GitHub CLI ist lokal im Projekt unter `tools/` installiert.

Login starten:

```bash
cd "/Users/carmelobonanno/Documents/Codex/2026-05-08/grill-me"
./github-login.sh
```

Wenn ein Code angezeigt wird:

1. `https://github.com/login/device` öffnen
2. Den angezeigten Code eingeben
3. GitHub CLI autorisieren

Status prüfen:

```bash
tools/gh_2.92.0_macOS_arm64/bin/gh auth status
```

## 2. Lokal in diesem Ordner ausführen

Im Terminal:

```bash
cd "/Users/carmelobonanno/Documents/Codex/2026-05-08/grill-me"
git init
git config user.name "Carmelo Bonanno"
git config user.email "carmelo.bonanno@bonanno-consulting.com"
git add .
git commit -m "Initial Bonanno Consulting website"
git branch -M main
git remote add origin https://github.com/DEIN-GITHUB-USER/wint-global.git
git push -u origin main
```

`DEIN-GITHUB-USER` durch deinen GitHub-Benutzernamen oder deine Organisation ersetzen.

## 3. GitHub Pages aktivieren

1. Im GitHub Repository öffnen: `Settings > Pages`
2. Unter `Build and deployment`:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/root`
3. Speichern.
4. Custom domain eintragen:

```txt
bonanno-consulting.com
```

Die Datei `CNAME` ist bereits im Projekt enthalten und enthält ebenfalls `bonanno-consulting.com`.

## 4. DNS für bonanno-consulting.com setzen

Beim DNS-Anbieter von `bonanno-consulting.com` diese Records setzen:

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

Optional für `www.bonanno-consulting.com`:

```txt
CNAME  www  DEIN-GITHUB-USER.github.io
```

## 5. HTTPS aktivieren

Wenn GitHub die Domain erkannt hat:

1. Wieder zu `Settings > Pages`
2. `Enforce HTTPS` aktivieren

DNS-Änderungen können einige Minuten bis 24 Stunden dauern.
