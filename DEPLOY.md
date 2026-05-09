# Deployment: GitHub Pages + Weiterleitung von bonanno-consulting.com

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
4. Keine Custom Domain in GitHub Pages eintragen, wenn `bonanno-consulting.com` per Weiterleitung beim Hoster liegt.

Die GitHub-Pages-Ziel-URL lautet:

```txt
https://cc-cbonanno.github.io/wint-global/
```

## 4. Weiterleitung bei Wint einrichten

Wenn DNS nicht auf GitHub Pages zeigen kann, im Wint-Panel eine permanente Weiterleitung einrichten:

```txt
Quelle: bonanno-consulting.com
Ziel:   https://cc-cbonanno.github.io/wint-global/
Typ:    301 permanent
```

Falls Wint eine `.htaccess`-Datei im Webspace verwendet, den Inhalt aus `redirect/.htaccess` in den Document Root von `bonanno-consulting.com` hochladen.

Falls nur eine HTML-Weiterleitung möglich ist, `redirect/index.html` hochladen.

Falls ein eigener Nginx-Serverblock möglich ist, `redirect/nginx.conf` verwenden.

## DNS-Alternative

Wenn später doch DNS möglich ist, statt Weiterleitung diese Records setzen und in GitHub Pages wieder `bonanno-consulting.com` als Custom Domain eintragen:

```txt
A     @     185.199.108.153
A     @     185.199.109.153
A     @     185.199.110.153
A     @     185.199.111.153
```
