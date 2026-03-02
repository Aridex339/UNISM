
# Mitwirken an UNISM

Schön das dich die regeln und abläufe interessieren. dabei werden folgenden regeln gefolgt.

## 🛠 Workflow

1. **Issue anlegen**
   - Erstelle vor größeren Änderungen ein Issue (z.B. Feature, Bug, Frage).
   - Nutze die vorhandenen Issue-Templates.

2. **Branching**
   - Features: `feat/<kurze-beschreibung>`  
     z.B. `feat/agent-registration`  
   - Bugfixes: `fix/<kurze-beschreibung>`  
     z.B. `fix/grpc-tls-config`
   - Dokumentation: `docs/<kurze-beschreibung>`

3. **Pull Requests**
   - Ziel-Branch: `main`
   - Beschreibe klar:
     - Was wurde geändert?
     - Wie wurde getestet?
     - Gibt es Breaking Changes?
   - Verknüpfe das passende Issue (`Closes #<nummer>`).

## 📝 Commit Messages

Halte Commit-Nachrichten kurz und eindeutig. Empfohlenes Schema:

- `feat: <kurze beschreibung>` – neue Funktion oder Modul
- `fix: <kurze beschreibung>` – Fehlerbehebung
- `docs: <kurze beschreibung>` – nur Dokumentation
- `refactor: <kurze beschreibung>` – interne Umstrukturierung ohne neues Feature
- `chore: <kurze beschreibung>` – Build/CI/Tooling, keine Feature-Änderungen

Beispiele:

- `feat: add basic agent registry`
- `fix: handle grpc tls handshake error`
- `docs: update readme with mvp roadmap`

## 🔐 Code- und Sicherheitsrichtlinien

UNISM beschäftigt sich mit Server-Management – Sicherheit ist zentral:

- Keine generischen „Arbitrary Command Execution“-Endpunkte.
- Tasks/Kommandos möglichst whitelisten und klar benennen.
- Keine Secrets in Commits pushen (Certs, Keys, Tokens etc.).
- Konfiguration über `.env`/Config-Dateien, nicht im Code hardcoden.

Security-relevante Änderungen bitte im PR extra hervorheben.

## 💻 Code-Style (Kurz)

- **Java (Backend)**: orientiere dich an üblichen Spring-Boot-Konventionen (CamelCase, Services/Controller/Repositories).
- **Python (Agent)**: PEP8, sinnvolle Modulstruktur (z.B. `core/`, `modules/`, `config/`).
- Linter/Formatter sind willkommen (z.B. `spotless` für Java, `black`/`ruff` für Python), sobald eingerichtet.

## 🔍 Tests

- Für neue Logik möglichst Unit- oder Integrationstests hinzufügen.
- Vor einem PR lokal sicherstellen, dass Tests durchlaufen (sobald Test-Setup steht).

## 💬 Fragen & Diskussion

- Nutze das Issue-Template **„Frage / Support“** für allgemeine Fragen.
- Für Design-/Architekturentscheidungen gerne ein eigenes „Design“-Issue anlegen.
- Technische Diskussionen zu konkreten Änderungen direkt im Pull Request führen.

Danke, dass du dazu beiträgst, UNISM zu einem stabilen und sicheren Open-Source-Projekt zu machen!
