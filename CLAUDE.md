# Projekt-Vorlage für vitos.app

Dieses Repo ist die Vorlage für Vitos Projekte. Jedes Projekt bekommt eine eigene Seite im Hub unter
`https://vitos.app/repo/<repo-name>/`. Der Text dort kommt **live aus diesem Repo** (`HUB.md`) und wird
nicht im Hub gepflegt. Nach einem Push ist der Hub spätestens 5 Minuten später aktuell.

## Wenn ein neues Projekt „wie in der Vorlage“ angelegt werden soll

1. **Repo anlegen** aus der Vorlage:
   `gh repo create vsvito420/<name> --public --template vsvito420/hub-projekt-vorlage --clone`
   Namen klein schreiben, mit Bindestrichen, ohne Umlaute.
2. **Projekt bauen**, dann `PROJEKTNAME` überall ersetzen.
3. **`README.md`** auf Englisch schreiben, für GitHub: kurz, Installation, Nutzung.
4. **`HUB.md`** auf Deutsch schreiben, für den Hub. Stil:
   - wenig Fließtext, lieber verschachtelte Listen
   - Abschnitte: *Was es zeigt / kann*, *Installieren*, *So funktioniert's*, *Siehe auch*
   - Bilder relativ einbinden (`docs/bild.png`), der Hub biegt die Pfade aufs Repo um
   - die erste `# H1` wird im Hub ausgeblendet
5. **Committen und pushen.**
6. **Im Hub eintragen** über den MCP-Server `vitos-hub`, Werkzeug `add_project`:
   ```json
   {
     "repo": "https://github.com/vsvito420/<name>",
     "file": "HUB.md",
     "title": "Lesbarer Titel",
     "description": "Ein Satz auf Deutsch.",
     "tags": ["informatik/linux/omarchy", "tool"],
     "link": "https://… (nur wenn es eine Live-Version gibt)"
   }
   ```
   - Tags wie bei den Hub-Seiten: Ein `/` macht den Tag verschachtelt, und ein oberster Tag mit dem
     Namen eines Bereichs hängt das Projekt an diesen Bereich (`informatik`, `musik`, `games`, `garten`, `sonstiges`).
   - Mit `list_projects` siehst du die vorhandenen Tags und kannst sie wiederverwenden.
7. **Prüfen:** `https://vitos.app/repo/<name>/` öffnen.

## Ändern

- Text ändern: `HUB.md` im Repo bearbeiten und pushen. Fertig, der Hub muss nicht angefasst werden.
- Titel, Tags oder Beschreibung ändern: `add_project` mit demselben Repo nochmal aufrufen.
- Aus dem Hub entfernen: `remove_project`.
