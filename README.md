# mikkel-agents

**Webseite mit Aufgaben-Baukasten: https://mikkel-thiemann.github.io/mikkel-agents/**
Dort Agent und Projekt wählen, Aufgabe eintippen und den fertigen Befehl kopieren.

Eine Sammlung von **Claude-Code-Agenten** (Subagents) für die tägliche Programmierarbeit –
auf Deutsch, ausgelegt auf schlanke Web- und Browser-Spiel-Projekte (Vanilla JS, Canvas, Three.js).

## Die Agenten

| Agent | Wofür |
|---|---|
| **feature-builder** | Baut ein neues Feature komplett fertig – von der Planung bis zum lauffähigen Code. |
| **bug-hunter** | Sucht Fehler und behebt die Ursache, nicht das Symptom. |
| **code-checker** | Review ohne Änderungen: echte Bugs, Sicherheit, Performance, Vereinfachung. |
| **web-game-dev** | Browser-Spiele: Spiellogik, Canvas/Three.js, Steuerung, Delta-Zeit, Performance. |
| **webseiten-bauer** | Baut ganze Webseiten mit HTML, CSS und JavaScript – ohne Build-Werkzeuge. |
| **erklaerbaer** | Erklärt Code und Fehlermeldungen einfach und verständlich. |
| **aufraeumer** | Refactoring bei exakt gleichem Verhalten. |
| **planer** | Zerlegt grosse Vorhaben in Schritte, bevor gebaut wird. |
| **test-schreiber** | Schreibt Tests, die echte Fehler finden, und lässt sie laufen. |

Für grössere Vorhaben – mehrere Dateien, mehrere Schritte – planen die arbeitenden Agenten
zuerst und arbeiten den Plan dann Schritt für Schritt ab.

## Installation

**Für alle Projekte** (global, empfohlen):

```bash
git clone https://github.com/mikkel-thiemann/mikkel-agents.git
cp mikkel-agents/agents/*.md ~/.claude/agents/
```

**Nur für ein einzelnes Projekt:**

```bash
cp mikkel-agents/agents/*.md dein-projekt/.claude/agents/
```

Unter Windows (PowerShell):

```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\agents"
Copy-Item mikkel-agents\agents\*.md "$HOME\.claude\agents\"
```

## Benutzung

Im Chat einfach den Agenten nennen:

```
bug-hunter: in MikkelRacer bleibt das Auto an der Wand hängen
web-game-dev: baue einen Doppelsprung ein
erklaerbaer: was macht die Datei world.js?
```

Claude Code wählt passende Agenten oft auch selbst aus – anhand der `description` im Kopf
jeder Agenten-Datei.

## Aufbau einer Agenten-Datei

Jeder Agent ist eine Markdown-Datei mit Frontmatter:

```markdown
---
name: bug-hunter
description: Wann dieser Agent benutzt werden soll.
tools: Read, Write, Edit, Glob, Grep, Bash
model: sonnet
---

Der Systemprompt des Agenten: Rolle, Vorgehen, Regeln.
```

- `name` – der Aufrufname
- `description` – entscheidet, wann Claude den Agenten von selbst vorschlägt
- `tools` – welche Werkzeuge er benutzen darf (weglassen = alle)
- `model` – `sonnet`, `opus` oder `haiku`

Eigene Agenten anlegen: Datei nach dem gleichen Muster in `agents/` ablegen.

## Lizenz

MIT
