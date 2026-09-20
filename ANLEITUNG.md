# GitHub einrichten – Schritt für Schritt

Alles, was ins Repo gehört, liegt in diesem Ordner (`scc\github\`). Auf diesem Rechner sind
weder `git` noch die GitHub-CLI installiert, deshalb geht es über die Webseite – dauert fünf
Minuten und braucht kein Programm.

## 1. Repo anlegen

1. github.com öffnen, anmelden, oben rechts **+ → New repository**.
2. **Repository name:** `SuperCoolCalculator`
3. **Description:** `SCC – Super Cool Calculator: bug tracker and issue reports`
4. **Public** auswählen.
5. Haken bei „Add a README file“ **weglassen** (die README bringen wir selbst mit).
6. **Create repository**.

## 2. Dateien hochladen

Auf der leeren Repo-Seite auf **uploading an existing file** klicken (oder direkt
`https://github.com/xXxRonaldxXx/SuperCoolCalculator/upload/main`).

Diese Dateien aus `scc\github\` hineinziehen:

- `README.md`
- `LICENSE`
- den ganzen Ordner `.github` (darin `ISSUE_TEMPLATE\bug_report.yml`,
  `feature_request.yml`, `config.yml`)

Windows blendet Ordner mit Punkt am Anfang manchmal aus – im Explorer unter „Ansicht“
**Ausgeblendete Elemente** einschalten, dann ist `.github` sichtbar. Ordner lassen sich in
das Upload-Feld ziehen, die Struktur bleibt erhalten.

Unten **Commit changes** drücken.

## 3. Issues einschalten

1. Im Repo auf **Settings → General → Features**: Haken bei **Issues** setzen.
   Wikis, Projects und Discussions kannst du auslassen.
2. Auf der Startseite rechts bei **About** das Zahnrad: Beschreibung eintragen, und bei
   **Website** später die CurseForge-Seite.
3. In `README.md` steht beim CurseForge-Link noch ein Platzhalter, und in
   `.github/ISSUE_TEMPLATE/config.yml` zeigt der erste Eintrag nur auf die CurseForge-
   Übersicht. Beides direkt auf GitHub nachtragen (Stift-Symbol), sobald die Projektseite
   steht.

## 4. CurseForge verknüpfen – der „Issues“-Knopf

Auf der CurseForge-Projektseite: **Manage Project → Settings**, Abschnitt mit den
Projekt-Links:

- **Issue Tracker URL:** `https://github.com/xXxRonaldxXx/SuperCoolCalculator/issues`
- **Source URL:** leer lassen, solange der Quellcode nicht öffentlich ist.

Danach steht auf der Projektseite rechts unter „Links“ ein **Issues**-Eintrag – genau wie
bei JEI – und er führt direkt zu deinen GitHub-Issues.

## 5. Der Link in der Mod selbst

Ist schon eingetragen. In `gradle.properties` steht:

```
mod_issues=https://github.com/xXxRonaldxXx/SuperCoolCalculator/issues
```

Die Adresse landet beim Bauen in `neoforge.mods.toml`. In der Modliste (Mods → SCC) hat
SCC damit einen eigenen Knopf, der zu denselben Issues führt. Ändert sich die Adresse,
reicht es, diese eine Zeile zu ändern und neu zu bauen.

## Später: Quellcode nachziehen

Wenn du den Code doch öffentlich machen willst, brauchst du `git` (git-scm.com). Dann im
Projektordner:

```bash
git init
git remote add origin https://github.com/xXxRonaldxXx/SuperCoolCalculator.git
git add .
git commit -m "SCC 1.1.0"
git push -u origin main
```

Vorher eine `.gitignore` anlegen, mindestens mit: `build/`, `.gradle/`, `run/`,
`run-server/`, `backups/`, `release/*.jar`.
