# E‑Auto 365 – App-Prototyp

Eine private, offlinefähige Fahrten- und Kostenbuch-App für Android- und Desktop-Browser. Die Daten bleiben im lokalen Browserprofil. Es gibt keine Anmeldung und keinen Cloud-Dienst.

## Funktionen

- Ladevorgänge mit Datum, Kilometerstand, kWh, Kosten, Ort/Anbieter und Notiz erfassen, bearbeiten und löschen.
- Sonstige Kosten nach Kostenart erfassen.
- Jahresübersicht mit Gesamtkosten, Ladekosten, sonstigen Kosten, geladenen kWh, gefahrenen Kilometern und Verbrauch.
- CSV-Export und -Import für die Excel-Blätter `Ladevorgaenge` und `Kosten`; vorhandene IDs werden beim Import aktualisiert.
- JSON-Backup und Wiederherstellung.

## Direkt öffnen

`index.html` kann im Browser geöffnet werden. Für die dauerhafte lokale Speicherung sollte die App über eine sichere Website-Adresse (HTTPS) aufgerufen werden. Auf Android lässt sie sich dann in Chrome über **⋮ → Zum Startbildschirm hinzufügen** als Web-App installieren und funktioniert nach dem ersten Aufruf offline.

Die Dateien in diesem Ordner sind eine fertige statische Web-App. Für eine Android-APK muss sie noch in eine Android-Hülle verpackt oder bei einem Hosting-Anbieter bereitgestellt und dann als Web-App installiert werden; in dieser Arbeitsumgebung ist kein Android-SDK vorhanden.

## Excel-Austausch

1. In der App unter **Excel-Austausch** die CSV für Ladevorgänge oder Kosten herunterladen.
2. In Excel öffnen oder über **Daten → Aus Text/CSV** importieren.
3. Für Daten aus der vorhandenen Arbeitsmappe das passende Blatt als CSV exportieren und in der App einlesen. Der Abgleich nutzt die ID.
4. Bewahre die JSON-Sicherung zusätzlich auf. Browserdaten können beim Löschen der Browserdaten oder beim Entfernen der App gelöscht werden.

Die `.xlsm`-Originaldatei wird von der App nicht verändert. Da ihre Eingabeblätter sehr ausgeblendet sind, sollte der CSV-Austausch zunächst mit einer Kopie der Arbeitsmappe erfolgen.

## Android-APK

Eine Anleitung für HTTPS-Bereitstellung und APK-Erstellung mit PWABuilder liegt in [APK-Erstellen.md](APK-Erstellen.md).

