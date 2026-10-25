# E‑Auto 365 als APK bereitstellen

Die Dateien im App-Paket sind eine Progressive Web App (PWA), keine fertige APK. Für den APK-Weg wird die App zuerst unter einer HTTPS-Adresse veröffentlicht und dann mit PWABuilder als Android-App verpackt. Dafür ist kein lokales Android-SDK nötig.

## 1. App-Dateien auf eine HTTPS-Adresse legen

Die Dateien in `E-Auto-365-App` müssen gemeinsam unter einer erreichbaren HTTPS-Adresse liegen. Ein kostenloser statischer Webhost wie GitHub Pages kann dafür verwendet werden.

Bei GitHub Pages: Repository anlegen, **den Inhalt** des Ordners hochladen (nicht den Ordner als zusätzliche Unterebene), Pages aktivieren und die erzeugte `https://…`-Adresse öffnen. Im Stamm der Adresse müssen mindestens `index.html`, `manifest.webmanifest`, `sw.js` und die Icon-Dateien erreichbar sein.

Die App speichert Fahrten und Kosten lokal im Browser. Bei einem öffentlichen statischen Host ist der App-Programmcode erreichbar, die in der App eingetragenen Fahrzeugdaten werden aber nicht an den Host übertragen. Für den Excel-Austausch nutzt du weiterhin den CSV-Export/Import.

## 2. App-Adresse prüfen

Öffne die HTTPS-Adresse auf dem Android-Handy in Chrome und prüfe, ob die App erscheint. Lege zuerst einen Testeintrag an und lade anschließend eine CSV-Sicherung herunter. Falls du nur ein App-Symbol auf dem Startbildschirm brauchst, genügt in Chrome **⋮ → Zum Startbildschirm hinzufügen**; eine APK ist dafür nicht nötig.

## 3. APK mit PWABuilder erzeugen

1. Öffne [PWABuilder](https://www.pwabuilder.com/) und gib die HTTPS-Adresse deiner App ein.
2. Wähle die Android-Paketierung und starte **Generate Package**.
3. Für eine APK zur privaten Installation lade ein **signiertes APK** herunter. Wenn nach der Signatur gefragt wird, wähle einen neuen Schlüssel. **Bewahre die heruntergeladene Keystore-Datei und die Zugangsdaten sicher auf**; spätere APK-Updates müssen mit demselben Schlüssel signiert werden.
4. Entpacke das PWABuilder-ZIP und kopiere die Datei mit der Endung `.apk` auf das Android-Handy.
5. Öffne die APK auf dem Handy. Android kann einmalig fragen, ob der verwendete Browser oder Dateimanager Apps aus dieser Quelle installieren darf.

PWABuilder nutzt für Android eine Trusted Web Activity. Damit die App ohne Browserleiste im Vollbild erscheint, muss zusätzlich die von PWABuilder erzeugte `assetlinks.json` auf derselben Website unter `/.well-known/assetlinks.json` erreichbar sein. Die Anleitung und Beispieldatei sind im Download-Paket von PWABuilder enthalten.

PWABuilder-Pakete setzen laut Dokumentation Android 7.0 oder neuer voraus. Für die private Installation per APK ist kein Play-Store-Konto erforderlich. Nur wenn du die App im Play Store veröffentlichen möchtest, benötigst du zusätzlich ein Play-Console-Entwicklerkonto.

### Offizielle Hinweise

- [PWABuilder: Android-Pakete erstellen](https://github.com/pwa-builder/PWABuilder/blob/main/docs/builder/android.md)
- [Android Developers: Trusted Web Activities](https://developer.android.com/develop/ui/views/layout/webapps/trusted-web-activities)
- [Google Play Console: Entwicklerkonto anlegen](https://support.google.com/googleplay/android-developer/answer/6112435?hl=de)
