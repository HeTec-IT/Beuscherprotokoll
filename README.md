# Filialprotokoll – Einrichtung

## 1. Firebase-Projekt
1. https://console.firebase.google.com → neues Projekt (z. B. `filialprotokoll-hetec`)
2. **Firestore Database** anlegen (Produktionsmodus)
3. **Authentication** → Sign-in-Methode → E-Mail/Passwort aktivieren
4. **Authentication** → Nutzer → eigenen Account manuell anlegen (E-Mail + Passwort)
5. Projekteinstellungen → „Web-App hinzufügen" → Config-Werte kopieren
6. In `index.html` den Block `FIREBASE_CONFIG` mit diesen Werten ersetzen

## 2. Firestore-Regeln
Firestore → Regeln → Inhalt von `firestore.rules` einfügen → Veröffentlichen

## 3. 60-Tage-Aufbewahrung (automatisches Löschen)
Firestore → TTL (im Menü „Time-to-live") → Richtlinie auf Collection-Group
`protokolle`, Feld `ablaufAm` anlegen. Ohne diesen Schritt bleiben alte
Einträge technisch bestehen, werden in der App aber nach 60 Tagen nicht
mehr angezeigt.

## 4. Outlook-Zieladresse (optional)
In `index.html` die Konstante `EMPFAENGER_EMAIL` setzen, falls „Per Outlook
senden" immer an dieselbe Adresse gehen soll. Leer lassen = Outlook öffnet
mit leerem An-Feld.

## 5. Hosting (GitHub Pages)
Neues Repo z. B. `hetec-it/Filialprotokoll`, alle Dateien (`index.html`,
`manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`) in den
Root oder `/docs`-Ordner, GitHub Pages aktivieren.
Erwartete URL: `https://hetec-it.github.io/Filialprotokoll/`

## 6. Auf dem Handy installieren
Live-URL öffnen → Anmelden → Browser-Menü → „Zum Home-Bildschirm
hinzufügen" / „App installieren".
