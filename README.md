# lenawiese.de

Statische, barrierearme Ein-Seiten-Website (reines HTML/CSS/JS, kein Build-Schritt, kein Tracking).

Enthält:
- `index.html` — die Seite selbst (Feld-Ansicht + Register mit Chronologie, Strategie, Vita, Publikationen, Kontakt, Impressum, Datenschutz)
- `fonts/` — lokal eingebundene Schriftdateien (Fraunces, Space Mono, Inter), damit keine Anfrage an Google-Server geht

## So bringst du die Seite online (GitHub Pages)

### 1. Repository anlegen
1. Auf [github.com](https://github.com) einloggen (oder Konto anlegen, falls noch nicht vorhanden).
2. Oben rechts auf **+** → **New repository**.
3. Name z. B. `lenawiese-website`, Sichtbarkeit **Public** (nötig für kostenloses GitHub Pages — der Quelltext ist dann einsehbar, aber es stehen ohnehin keine privaten Daten darin).
4. **Create repository** klicken, sonst nichts ankreuzen (kein README, keine .gitignore — die bringen wir schon mit).

### 2. Diesen Ordner hochladen
Im Terminal in diesem Ordner:

```bash
git init
git add index.html fonts README.md
git commit -m "Initiale Version der Website"
git branch -M main
git remote add origin https://github.com/DEIN-NUTZERNAME/lenawiese-website.git
git push -u origin main
```

(`DEIN-NUTZERNAME` und den Repo-Namen anpassen, falls anders gewählt.)

### 3. GitHub Pages aktivieren
1. Im Repository auf **Settings** → **Pages**.
2. Unter **Build and deployment** → **Source**: `Deploy from a branch`.
3. Branch: `main`, Ordner: `/ (root)`. Speichern.
4. Nach ein bis zwei Minuten ist die Seite unter `https://DEIN-NUTZERNAME.github.io/lenawiese-website/` erreichbar.

### 4. Eigene Domain lenawiese.de verbinden
1. Weiterhin unter **Settings** → **Pages** → Feld **Custom domain**: `www.lenawiese.de` eintragen, speichern.
   GitHub legt automatisch eine Datei `CNAME` mit diesem Inhalt im Repo an.
2. Bei Strato in der **Domainverwaltung** von lenawiese.de folgende DNS-Einträge setzen:
   - **CNAME** für `www` → `DEIN-NUTZERNAME.github.io`
   - **A-Einträge** für die nackte Domain `lenawiese.de` (ohne www) auf die vier GitHub-Pages-IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
3. Warten, bis die DNS-Änderung greift (oft wenige Minuten, kann bis zu 24 Std. dauern).
4. Zurück in GitHub **Settings → Pages**: Haken bei **Enforce HTTPS** setzen, sobald die Option anklickbar ist (GitHub braucht dafür ein gültiges DNS).
5. Der bisherige Strato-Baukasten bleibt bis zur DNS-Umstellung unverändert erreichbar — du kannst also in Ruhe vorher unter der `github.io`-Adresse testen.

## Änderungen später einspielen

Datei lokal bearbeiten, dann:

```bash
git add -A
git commit -m "Beschreibung der Änderung"
git push
```

Nach ein bis zwei Minuten ist die Änderung live.

## Rechtliches — was noch zu prüfen ist

Impressum und Datenschutzerklärung in `index.html` (Register-Reiter „Impressum" / „Datenschutz") sind als sorgfältiger Entwurf auf Basis der angegebenen Daten (Lena Wiese, Musfeldstraße 110, 47053 Duisburg, kontakt@lenawiese.de, privat/nicht-kommerziell) erstellt. Bitte vor Live-Schaltung prüfen:
- Stimmen Anschrift und E-Mail noch?
- Falls die Seite künftig doch wirtschaftlich genutzt wird (Honorare, Verkäufe über die Seite), müssten USt-Angaben ergänzt werden.
- Diese Texte ersetzen keine Rechtsberatung im Einzelfall.
