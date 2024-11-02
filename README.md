
# Discord Rich Presence Script

Dieses Python-Skript ermöglicht die Integration von Discord Rich Presence. 
Es verwendet die `pypresence`-Bibliothek, um Benutzerdetails auf Discord anzuzeigen, 
einschließlich Status, Beschreibung, Zeitstempel und Symbole. Zudem ist es mit einem 
Tray-Icon ausgestattet, um die Steuerung zu erleichtern.

## Funktionen

- **Discord Rich Presence**: Anzeige von benutzerdefiniertem Status und weiteren Informationen auf Discord.
- **Konfigurierbares Setup**: Anpassung der Anzeigeoptionen wie Status, Details, große und kleine Symbole sowie deren Beschriftungen.
- **Tray-Icon**: Integration eines Tray-Icons für eine einfache Steuerung (z. B. Start/Stopp).
- **Zeitstempel**: Optionale Anzeige des Startzeitpunkts im Status.

## Features

- Konfigurierbare `config.ini`-Datei zur einfachen Anpassung.
- Unterstützung für benutzerdefinierte Symbole und Links im Discord-Status.
- Autonomer Betrieb im Hintergrund mithilfe von `threading`.

## Voraussetzungen

Installiere die folgenden Module, bevor du das Skript ausführst:

```bash
pip install pypresence pillow pystray webbrowser
```

## Einrichtung

1. **Konfigurationsdatei**: Beim ersten Start des Skripts wird eine `config.ini`-Datei im Verzeichnis erstellt. 
   Bearbeite diese Datei, um deine bevorzugten Einstellungen anzupassen. Setze `client_id` und passe die Details an.

   Beispiel für `config.ini`:

   ```ini
   [RichPresence]
   # Erstelle eine Client-ID für deine Anwendung: https://discord.com/developers/applications
   client_id = DEIN_CLIENT_ID
   state = Dein Status
   details = Weitere Details
   # Setze auf 1, um die Startzeit anzuzeigen
   start = 1
   large_image = dein_großes_bild
   large_text = Text für großes Bild
   small_image = dein_kleines_bild
   small_text = Text für kleines Bild
   button1_label = Button 1
   button1_url = https://beispiel.com
   button2_label = Button 2
   button2_url = https://beispiel.com
   # Base64-Code für das Tray-Icon
   tray_icon_base64 = ICON_BASE64_CODE
   ```

2. **Discord Developer Portal**: Erstelle eine Anwendung im 
   [Discord Developer Portal](https://discord.com/developers/applications) und erhalte eine `client_id`, 
   die du in der `config.ini`-Datei einträgst.

## Ausführen des Skripts

Starte das Skript mit:

```bash
python py-presence.py
```

Das Tray-Icon erscheint in der Taskleiste und ermöglicht eine einfache Steuerung des Rich Presence Status.

## Anpassung des Tray-Icons

Das Tray-Icon verwendet ein Base64-codiertes Bild, das direkt in die `config.ini`-Datei eingefügt wird. 
Hierfür kann ein beliebiges Icon-Bild in Base64 umgewandelt und im Wert von `tray_icon_base64` hinterlegt werden.

## Hinweis

Dieses Skript läuft im Hintergrund und aktualisiert den Discord-Status basierend auf den Einstellungen in der `config.ini`. 
Für eine erneute Konfiguration muss das Skript neu gestartet werden.

## Lizenz

Dieses Projekt steht unter der MIT-Lizenz.

## Verwendete Bibliotheken

Dieses Projekt verwendet folgende Open-Source-Bibliotheken:

- [pypresence](https://github.com/qwertyquerty/pypresence) - zur Interaktion mit Discord Rich Presence.
- [Pillow](https://python-pillow.org/) - für Bildverarbeitung und die Erstellung des Tray-Icons.
- [pystray](https://github.com/moses-palmer/pystray) - zur Anzeige und Steuerung eines Tray-Icons.
- [webbrowser](https://github.com/moses-palmer/pystray) - Erlaubt URLs mit dem Standard System Browser zu öffnen.
