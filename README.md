# NEXOVIA Akademie

Dies ist ein statisches Prototyp‑Portal für die NEXOVIA Akademie.  
Es basiert auf dem bereitgestellten Corporate‑Identity‑Guide und dient als Ausgangspunkt für die finale Umsetzung auf eurer Domain.

## Struktur

Die Dateien sind in folgende Bereiche gegliedert:

- **index.html** – Hauptseite nach Login mit Navigation zu den Unterkategorien
- **login.html** – einfache Login‑Maske (kein echtes Backend)
- **onboarding/** – Inhalte für das Onboarding (Willkommen, Produktwissen, Verkaufsleitfäden, Einwandbehandlung)
- **schulungen/** – Trainingsmaterialien (Videos, Schritt‑für‑Schritt Anleitungen, Best Practices)
- **prozesse/** – Dokumentierte Abläufe (CRM Nutzung, Angebot erstellen, Follow‑ups)
- **faq/** – Häufig gestellte Fragen
- **admin/** – Admin‑Dashboard (Benutzerverwaltung, Aktivitätsübersicht, Chats, Events, News)

Gemeinsame Gestaltungselemente wie Farben und Typografie werden in `css/style.css` definiert. Logos und Icons liegen im Ordner `assets`.

## Hosting & Authentifizierung

Um die Seite passwortgeschützt zu hosten, sind serverseitige Maßnahmen erforderlich. Für All‑Inkl‑Hosting (Apache):

1. **Dateien hochladen:** Lade den gesamten Ordnerinhalt (z. B. in einen Unterordner `akademie/`) auf deinen Webspace.
2. **Verzeichnisschutz:** Lege im Ordner eine `.htaccess`‑Datei mit folgendem Inhalt an:

   ```
   AuthType Basic
   AuthName "NEXOVIA Akademie"
   AuthUserFile /pfad/zu/.htpasswd
   Require valid-user
   ```
3. **Benutzer anlegen:** Erstelle eine `.htpasswd`‑Datei mit Nutzername und verschlüsseltem Passwort. Du kannst dies mit einem Tool wie `htpasswd` generieren oder online.
4. **Domain verbinden:** Richte einen Subdomain‑Alias wie `akademie.nexovia-marketing.com` oder einen Unterordner `nexovia-marketing.com/akademie` ein und verweise ihn auf den hochgeladenen Ordner.

Für die im Admin‑Dashboard genannten Funktionen (Benutzerverwaltung, E‑Mail‑Versand, Aktivitätsprotokoll etc.) ist ein serverseitiges System nötig (z. B. PHP, Node.js, Django, Datenbank). Dieses Prototyp‑Portal zeigt nur das Frontend‑Layout. Funktionen müssen durch eine Web‑Anwendung ergänzt werden.

## Anpassung & Skalierung

- **Logos und Farben:** Ersetze die Grafiken im Ordner `assets` durch deine finalen Vektorlogos (SVG/PNG) und passe bei Bedarf die Farbvariablen in `css/style.css` an.
- **Inhalte:** Alle `.html`‑Dateien können mit echtem Inhalt, Download‑Links (nur für Checklisten) oder eingebetteten Videos ergänzt werden.
- **Admins:** Weitere Administratoren lassen sich durch Anlegen zusätzlicher Benutzer in deiner .htpasswd bzw. in deiner späteren Web‑Anwendung realisieren.
- **Benutzerzahl:** Der verwendete Verzeichnisschutz ist nicht begrenzt. Für größere Teams ist allerdings ein vollwertiges CMS/Wiki (z. B. BookStack oder Wiki.js) empfehlenswert.

Dieses Repository dient als Startpunkt. Für produktive Nutzung sollte ein Entwickler die dynamischen Funktionen implementieren und Sicherheitsaspekte prüfen.