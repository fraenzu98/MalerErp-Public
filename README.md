# WerkDesk

Offerten, Rechnungen und Mahnungen für Handwerksbetriebe in der Schweiz. Mit QR-Rechnung, MWST, eigenem Briefpapier und automatischer Datensicherung.

**[WerkDesk herunterladen](https://github.com/fraenzu98/MalerErp-Public/raw/main/WerkDesk_Setup.exe)** · [Was ist neu?](https://fraenzu98.github.io/MalerErp-Public/changelog.html)

---

## Funktionen

- **Kunden** mit Historie aller Offerten und Rechnungen
- **Offerten** aus einem eigenen Leistungskatalog, mit Kategorien, Rabatt und Fotodokumentation; angenommene Offerten werden per Klick zum Rechnungsentwurf
- **Rechnungen** mit Swiss QR-Rechnung, MWST, Rappenrundung und fortlaufender Nummer pro Jahr
- **Mahnwesen** in zwei Stufen, überfällige Rechnungen werden automatisch erkannt
- **Dashboard** mit offenen Forderungen, Umsatz des Monats und überfälligen Rechnungen
- **Belegdesign** mit drei Vorlagen (Klassisch, Modern, Kompakt) oder deinem eigenen Briefpapier als PDF
- **Treuhand-Export** als CSV
- **Benutzer und Rollen** (Administrator, Mitarbeiter) mit Logbuch aller Änderungen
- **Automatische Updates** und tägliche Datensicherung

## Systemvoraussetzungen

- Windows 10 oder 11, 64 Bit
- Administratorrechte für die Installation
- Eine .NET-Installation ist nicht nötig, WerkDesk bringt alles mit.

## Installation

1. `WerkDesk_Setup.exe` herunterladen und ausführen.
2. Falls Windows SmartScreen warnt: **Weitere Informationen** und dann **Trotzdem ausführen** wählen.
3. Nach der Installation WerkDesk starten.

## Ersteinrichtung

Beim ersten Start führt WerkDesk durch folgende Schritte:

1. **Speicherort der Datenbank:** lokal auf diesem PC (Standard) oder auf einem Netzlaufwerk für mehrere Arbeitsplätze (siehe unten).
2. **Lizenz:** die `.license`-Datei auswählen, die du per E-Mail erhalten hast.
3. **Administrator anlegen:** Benutzername und Passwort (mindestens 8 Zeichen) für den ersten Zugang festlegen.

Danach unter **Admin & Setup** einrichten:

- **Firmen-Einstellungen:** Adresse, Telefon, E-Mail, Speicherort der PDFs. Firmenname und IBAN stammen aus der Lizenz.
- **MWST:** Wenn dein Betrieb MWST-pflichtig ist, Häkchen setzen, Satz (z.B. 8.1 %) und MWST-Nummer (z.B. `CHE-123.456.789 MWST`) eintragen. Preise im Leistungskatalog verstehen sich dann exklusive MWST.
- **Dokumenten-Vorlagen:** Logo, Farbe, Schrift, Vorlage oder Briefpapier, Standardtexte. Mit **Vorschau** siehst du das Ergebnis sofort.
- **Leistungskatalog:** deine Leistungen mit Einheit und Preis.
- **Benutzer:** weitere Zugänge anlegen. Neue Benutzer setzen beim ersten Login ihr eigenes Passwort.

## Arbeiten mit Rechnungen

- Eine Rechnung startet als **Entwurf** und kann beliebig angepasst werden. Ein Entwurfs-PDF ist als solches markiert und enthält keinen Zahlteil.
- Beim **Buchen** erhält die Rechnung ihre definitive Nummer (z.B. `2026-R001`) und ist danach gesperrt.
- Korrekturen an gebuchten Rechnungen: im Kundenfenster den Status der Rechnung auf **Storniert** setzen und eine neue Rechnung erstellen.
- Zahlungseingänge und Mahnungen: im Dashboard per Rechtsklick auf die Rechnung **Als bezahlt markieren** oder **Mahnung generieren**.

## Briefpapier

Unter **Admin & Setup > Dokumenten-Vorlagen** kannst du dein Briefpapier als PDF hinterlegen:

- Seite 1 des PDFs liegt unter der ersten Belegseite, eine allfällige Seite 2 unter allen Folgeseiten.
- Firmenkopf und Logo von WerkDesk entfallen dann, weil sie auf dem Briefpapier stehen.
- Die Seitenränder so einstellen, dass der Text nicht in Kopf- oder Fusszeile des Briefpapiers läuft (typisch oben 45 mm, unten 25 mm).
- Der QR-Zahlteil wird immer ohne Briefpapier gedruckt, wie es die Norm verlangt.

## Mehrere Arbeitsplätze

Die Datenbank kann auf einem Netzlaufwerk liegen, damit mehrere PCs gemeinsam arbeiten. Empfohlen ist das für **2 bis 3 Arbeitsplätze im selben Büronetz**. Über VPN oder eine schwache WLAN-Verbindung steigt das Risiko beschädigter Daten.

- Auf jedem PC WerkDesk installieren und bei der Ersteinrichtung dieselbe Datenbankdatei auf dem Netzlaufwerk wählen.
- Die Lizenzdatei auf jedem PC einspielen.
- Briefpapier und Backups liegen automatisch neben der Datenbank und sind so für alle Arbeitsplätze erreichbar.

## Datensicherung

- WerkDesk erstellt beim ersten Start jedes Tages automatisch ein Backup. Die letzten 30 Stände bleiben erhalten.
- Standardordner ist `Backups` neben der Datenbank. Unter **Admin & Setup > Firmen-Einstellungen > Datenbank & Backup** kannst du einen anderen Ordner wählen oder mit **Jetzt sichern** sofort ein Backup erstellen.
- Bei jedem Start wird die Datenbank geprüft. Ist sie beschädigt, zeigt WerkDesk das letzte Backup an.
- **Wiederherstellen:** WerkDesk auf allen Arbeitsplätzen schliessen, die gewünschte Backup-Datei kopieren und über die bestehende `appdata.db` legen.
- Tipp: Den Backup-Ordner zusätzlich auf einem externen Datenträger oder in einer Cloud-Ablage sichern.

## Lizenz

- Die Lizenz gilt für deinen Betrieb: Firmenname und IBAN sind fest darin hinterlegt und erscheinen auf allen Belegen.
- 30 Tage vor Ablauf erinnert WerkDesk beim Start.
- Nach Ablauf läuft WerkDesk im **Nur-Lesen-Modus**: Alle Belege bleiben einsehbar, PDFs und Zahlungseingänge sind weiter möglich, neue Offerten und Rechnungen erst wieder mit einer gültigen Lizenz. So bleiben deine Unterlagen für die gesetzliche Aufbewahrung immer zugänglich.
- Eine neue Lizenz spielst du unter **Admin & Setup > Firmen-Einstellungen > Neue Lizenzdatei importieren** ein. Eine fehlerhafte Datei ersetzt die bestehende Lizenz nicht.
- Für ein zusätzliches oder anderes Bankkonto wird eine neue Lizenz benötigt.

## Updates

WerkDesk prüft beim Start, ob eine neue Version verfügbar ist, und bietet die Installation an. Jedes Update wird vor der Installation anhand seiner Prüfsumme kontrolliert.

## Wo liegen meine Daten?

| Was | Ort (Standard) |
|--|--|
| Datenbank | `C:\ProgramData\WerkDesk\appdata.db` oder der bei der Einrichtung gewählte Ort |
| Backups | Ordner `Backups` neben der Datenbank |
| PDFs (Offerten, Rechnungen, Mahnungen, Fotos) | `Dokumente\WerkDesk` oder der in den Einstellungen gewählte Ordner |
| Lizenz | `C:\ProgramData\WerkDesk\lizenz.license` |
| Fehlerprotokoll | `C:\ProgramData\WerkDesk\logs` |

Wird ein PDF neu erzeugt, verschiebt WerkDesk die frühere Fassung in den Unterordner `_Archiv`.

## Häufige Fragen

**Ich habe mein Passwort vergessen.**
Ein Administrator kann unter **Benutzer** ein neues Initialpasswort setzen. Beim nächsten Login wird es geändert.

**WerkDesk meldet, die Datenbank sei beschädigt.**
Nicht weiterarbeiten. Alle Arbeitsplätze schliessen und das zuletzt angezeigte Backup zurückkopieren (siehe Datensicherung).

**Kann ich die IBAN ändern?**
Die IBAN ist an die Lizenz gebunden. Für ein neues Konto erhältst du eine neue Lizenzdatei.

**Wo sehe ich, was sich in einem Update geändert hat?**
In den [Änderungen](https://fraenzu98.github.io/MalerErp-Public/changelog.html).
