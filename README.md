# WWW

Quellcode der Website **www.dorfcode.com**.

Aktuell: einfache statische „Im Aufbau“-Seite.

## Dateien

- `index.html` – Startseite („Im Aufbau“)
- `404.html` – Fehlerseite, leitet zur Startseite weiter
- `favicon.svg` – Icon
- `CNAME` – eigene Domain für GitHub Pages (`www.dorfcode.com`)
- `.nojekyll` – Dateien unverändert ausliefern (kein Jekyll-Build)

## Lokal ansehen

```bash
python3 -m http.server 8000
# dann http://localhost:8000 öffnen
```

## Veröffentlichen mit GitHub Pages

1. Im Repository: **Settings → Pages**
2. *Source*: „Deploy from a branch“, Branch `main`, Ordner `/ (root)` → **Save**
3. Unter *Custom domain* steht `www.dorfcode.com` (kommt aus der `CNAME`-Datei).
4. Beim Domain-Anbieter folgende DNS-Einträge anlegen:

   | Typ   | Name  | Wert                  |
   |-------|-------|-----------------------|
   | CNAME | `www` | `dorfcode.github.io`  |
   | A     | `@`   | `185.199.108.153`     |
   | A     | `@`   | `185.199.109.153`     |
   | A     | `@`   | `185.199.110.153`     |
   | A     | `@`   | `185.199.111.153`     |

   (Die A-Einträge sorgen dafür, dass auch `dorfcode.com` ohne `www` funktioniert.)
5. Nach der DNS-Umstellung (kann bis zu 24 h dauern) in den Pages-Einstellungen **Enforce HTTPS** aktivieren.

Hinweis: Solange die `CNAME`-Datei existiert, leitet `https://dorfcode.github.io/www/` auf `www.dorfcode.com` um. Wer die Seite **vor** der DNS-Einrichtung testen will, entfernt kurz die Custom Domain in den Pages-Einstellungen.
