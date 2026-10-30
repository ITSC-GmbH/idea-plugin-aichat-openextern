# AI Chat Open External (IntelliJ IDEA Plugin)

`idea-plugin-aichat-openextern` ist ein IntelliJ IDEA-Plugin zum schnellen und nahtlosen Öffnen des Markdown-Transkripts (`transcript.md`) des aktuell sichtbaren oder jüngsten AI-Chats in einem externen Editor (z. B. **Typora**, **VS Code**, **Obsidian**, **Neovim**). Zusätzlich kann eine Bereinigung / Filterung erfolgen.

## Übersicht und Funktionsweise aus Anwendersicht

### Problemstellung und Nutzen
Im integrierten AI-Chat der IDE ist die Dokumentation und das Weiterverarbeiten längerer Chatverläufe oft umständlich, da UI-Kopierfunktionen meist nur einzelne Antworten erfassen. Die IDE speichert jedoch vollständige Markdown-Transkripte aller Sitzungen unter `~/.junie/sessions/<session_id>/transcript.md`.

Dieses Plugin schließt die Lücke: Mit einem einzigen Klick oder Tastenkürzel wird das Transkript des aktuell fokussierten Chat-Reiters ermittelt und direkt im bevorzugten externen Programm gestartet.

### Hauptfunktionen
- **Erkennung des aktiven Chats:** Erkennt den Titel des im Editor-Tab geöffneten Chat-Tabs und ordnet ihn der passenden Sitzungs-ID in `~/.junie/sessions/index.jsonl` zu.

  > [!note]
  >
  > Derzeit funktioniert die Erkennung des angezeigten Chats nur, wenn der Chat in einem Editor-Tab geöffnet ist. Wird lediglich der "AI Chat View" verwendet, ist das nicht möglich, es wird immer der jüngste Chat geöffnet.
- **Automatischer Fallback:** Ist kein Chat-Tab explizit fokussiert, wird automatisch das jüngste Transkript des aktuellen Projekts geöffnet.
- **Konfigurierbares Zielprogramm:** Der Name oder Pfad des externen Programms kann flexibel in den IDE-Einstellungen angepasst werden (Standard: `typora`).
- **Menüintegration:** Verfügbar im Menü `Tools`,.

## Konfiguration in der IDE

1. IDE-Einstellungen öffnen über `File -> Settings` (unter macOS: `IntelliJ IDEA -> Settings`) bzw. `Ctrl+Alt+S`.
2.  **Tools -> AI Chat Open External**.
3. Im Feld **Externes Programm (Binary oder Pfad)** den gewünschten Befehl eingeben:
   - `typora` (Standard)
   - `code` (für Visual Studio Code)
   - oder den absoluten Pfad, z. B. `/usr/bin/typora` oder `/opt/typora/Typora`
4. **Apply** bzw. **OK**.
