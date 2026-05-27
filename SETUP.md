# Setup-Checkliste

Alles was ihr einmalig eintragen / einrichten müsst.

---

## 1. Formspree einrichten (Formular → E-Mail)

- [ ] Auf https://formspree.io kostenlos registrieren
- [ ] „New Form" anlegen → Name: „Moritz Martin Anfragen"
- [ ] Eure E-Mail eintragen: Moritz.Martin@lbs-sued.de
- [ ] Form-ID kopieren (sieht aus wie: xpwzabcd)
- [ ] In index.html suchen nach: `EURE-FORM-ID`
- [ ] Ersetzen mit eurer ID, z.B.: `xpwzabcd`
- [ ] Ergebnis: `action="https://formspree.io/f/xpwzabcd"`

---

## 2. GitHub Pages aktivieren

- [ ] Repository auf github.com anlegen: `lbs-moritzmartin`
- [ ] Alle Dateien hochladen (index.html, README.md, .cursorrules, SETUP.md)
- [ ] Repository → Settings → Pages
- [ ] Source: „Deploy from a branch"
- [ ] Branch: main / Ordner: / (root)
- [ ] Save klicken
- [ ] Nach 1–2 Minuten live unter: `https://[username].github.io/lbs-moritzmartin`

---

## 3. Eigene Domain / Wix-Anbindung

**Option A – Subdomain von lbs-moritzmartin.de (empfohlen)**

Bei eurem Domain-Anbieter (wo lbs-moritzmartin.de registriert ist):
- [ ] DNS-Einstellungen öffnen
- [ ] Neuen CNAME-Eintrag anlegen:
  - Name: `anfrage`
  - Wert: `[username].github.io`
- [ ] In GitHub Pages → Custom Domain: `anfrage.lbs-moritzmartin.de` eintragen
- [ ] „Enforce HTTPS" aktivieren
- [ ] Ergebnis: Seite läuft unter `https://anfrage.lbs-moritzmartin.de`

**Option B – Wix Redirect**

Falls die Domain bei Wix liegt:
- [ ] Wix Dashboard → Domains → DNS-Einstellungen
- [ ] CNAME wie oben eintragen
- [ ] Wix leitet dann automatisch weiter

---

## 4. Google Tag Manager (für Ads-Tracking)

- [ ] Auf tagmanager.google.com einloggen
- [ ] Neuen Container anlegen → Web
- [ ] GTM-ID kopieren (Format: GTM-XXXXXXX)
- [ ] In index.html die zwei Stellen mit `GTM-XXXXXXX` befüllen
- [ ] Die `<!-- -->` Kommentare um den GTM-Code entfernen
- [ ] Im GTM: Google Analytics 4 Tag einrichten
- [ ] Im GTM: Google Ads Conversion Tag einrichten
- [ ] Im GTM: Trigger „Form Submit" auf den Button `#submit-btn` setzen

---

## 5. Meta Pixel

- [ ] Auf business.facebook.com → Events Manager
- [ ] Neuen Pixel erstellen
- [ ] Pixel-ID kopieren (16-stellige Zahl)
- [ ] In index.html `EURE-PIXEL-ID` ersetzen
- [ ] Kommentare um den Pixel-Code entfernen
- [ ] Im JS-Teil `fbq('track', 'Lead')` Kommentar entfernen → feuert bei Formular-Absenden

---

## 6. Google Ads Conversion-Tracking

- [ ] In Google Ads → Tools → Conversions → Neue Conversion
- [ ] Typ: Website
- [ ] Conversion-Aktion: „Lead / Anfrage"
- [ ] Conversion-ID und Label kopieren (Format: AW-XXXXXXXXX/XXXXXXXXXXX)
- [ ] In index.html `AW-XXXXXXXX/XXXXXXXXX` ersetzen
- [ ] Kommentar beim gtag-Aufruf entfernen

---

## 7. Foto von Moritz einbauen

Im Hero-Bereich steht aktuell ein Platzhalter „MM".
- [ ] Profifoto von Moritz als `moritz.jpg` in den Projektordner legen
- [ ] In index.html das `<div class="person-photo">MM</div>` ersetzen mit:
```html
<img src="moritz.jpg" alt="Moritz Martin" class="person-photo" style="object-fit:cover;">
```

---

## 8. Echte Kundenbewertungen eintragen

- [ ] Google My Business aufrufen → Bewertungen kopieren
- [ ] In index.html die drei Review-Cards mit echten Texten & Namen befüllen
- [ ] Initialen in den Avatar-Bubbles anpassen

---

## 9. Impressum & Datenschutz

- [ ] Impressum-Seite URL eintragen (kann auf lbs-moritzmartin.de/impressum verlinken)
- [ ] Datenschutz-URL eintragen
- [ ] In index.html alle `href="#"` bei Impressum/Datenschutz durch echte URLs ersetzen

---

## Änderungen deployen (nach dem Setup)

```bash
# In Cursor Terminal oder GitHub Desktop:
git add .
git commit -m "Was wurde geändert"
git push

# → Automatisch live in ~60 Sekunden
```

---

## Support & Fragen

Bei technischen Fragen: Claude (claude.ai) fragen und `.cursorrules` + den relevanten Code-Abschnitt zeigen.
