# App Store Connect — Reviewer Notes

Dieser Text wird im App-Store-Connect-Submission-Formular unter
**"App Review Information → Notes"** eingefügt. Er erklärt dem
Apple-Reviewer, wie die App ohne Konto funktioniert und wie er
Pro-Content prüfen kann.

---

## App-Beschreibung in Kurzform
Gaslight ist eine accountless Couples-Party-Game-App mit mehreren
Mini-Spielen. Es gibt **keine Registrierung, kein Login, keinen Server**
mit Nutzerdaten. Alle Free-Spiele sind sofort beim ersten App-Start
spielbar.

## Pro-Content / Subscription
Erweiterte Kategorien (insbesondere die **Spicy-Kategorie für 17+**)
sind hinter einem optionalen Abo:

- **Gaslight Pro Weekly** — 4,99 €/Woche, mit 3-tägiger kostenloser
  Testphase
- **Gaslight Pro Yearly** — 24,99 €/Jahr

Beide Pläne hängen am Entitlement `pro` (gemanaged über RevenueCat).

## Reviewer-Zugang zu Pro-Content

Wir stellen dem Reviewer einen **kostenlosen Apple Offer Code (100 %
Off)** zur Verfügung, der das Pro-Abo für die Reviewer-Periode
freischaltet.

**Promo-Code:** `___________________`
_(wird kurz vor Submission in App Store Connect → Subscriptions →
Offer Codes generiert, siehe Anleitung unten)_

**Einlösung in der App (empfohlen):**
1. App öffnen (kein Login nötig)
2. Auf einer gelockten Spiel-Kachel tippen → Paywall öffnet sich
3. Unter dem CTA: **"Code einlösen"** antippen
4. Apples natives Code-Redemption-Sheet erscheint
5. Code eingeben → Pro-Entitlement ist sofort aktiv
6. Paywall schließt sich, alle Pro-Inhalte sind freigeschaltet

**Alternative System-Einlösung:**
Einstellungen → Apple-Account → Geschenkkarte oder Code einlösen.
Funktioniert ebenfalls.

**Alternative Sandbox-Kauf:**
Falls der Promo-Code-Pfad nicht funktioniert: ein Sandbox-Apple-ID-Kauf
über das normale Paywall-Sheet kostet im Sandbox nichts. Reviewer kann
jeden Plan auswählen und durchklicken.

---

## Promo-Code generieren (interne Anleitung — VOR Submission)

Apple Offer Codes funktionieren über App Store Connect, nicht über
RevenueCat. Schritt für Schritt:

1. **App Store Connect** → My Apps → Gaslight
2. Tab **"Subscriptions"** oben
3. Im Subscription-Group auf **"Gaslight Pro Yearly"** klicken
   (Yearly bietet längere Laufzeit als Weekly, ideal für Review)
4. Linke Sidebar: **"Subscription Prices"** → unten **"Offer Codes"**
   → **"+ Set Up Offer Codes"**
5. **"Create First Code"** → Name z.B. `gaslight-review-jun26`
6. **Customer Eligibility**: *"New Subscribers"* + *"Existing
   Subscribers"* + *"Expired Subscribers"* alle aktivieren (so kann
   Reviewer ihn auf jedem Status einlösen)
7. **Offer Type**: **"Pay As You Go"** oder **"Pay Up Front"** — wähle
   **"Free"** als Pay-Type, **Duration: 1 Month** (lang genug für die
   ganze Review-Periode + Re-Submissions, kurz genug damit nichts
   passiert wenn der Code leakt)
8. **Number of Codes**: `5` (Puffer für Re-Submissions oder mehrere
   Reviewer)
9. **"Generate Codes"** → die Codes erscheinen sofort, als .csv
   downloadbar
10. Einen davon hier in dieses Dokument unter **"Promo-Code:"**
    einsetzen
11. App Store Connect → Submission → "App Review Information" →
    Notes-Feld mit diesem aktualisierten Dokument-Inhalt aktualisieren

**Wichtig:** Offer Codes funktionieren NUR im Production-Build, nicht
im Sandbox. Heißt: der Code geht ERST mit dem TestFlight-Build oder
nach App-Store-Approval. Während der Review hat Apple Zugang zum
Production-Build, also passt das.

## Age Rating
**17+** — App enthält in der Spicy-Kategorie Inhalte mit erotischen /
sexuellen Themen. Diese Kategorie ist nur über das Pro-Abo zugänglich.

## Privacy / Daten
- Keine eigenen User-Accounts, kein eigener Server.
- Datenverarbeitung ausschließlich via Apple StoreKit + RevenueCat
  (anonyme `appUserID` pro App-Install, Subscription-Status).
- Lokale Speicherung (AsyncStorage): Favoriten, optionaler Anzeigename,
  Spracheinstellung — verlassen das Gerät nicht.
- DeviceMotion-Sensoren werden für das tiltreaktive Liquid-Glass-UI
  genutzt; die Sensordaten werden ausschließlich auf dem Gerät
  verarbeitet.

**Privacy Policy:** https://appgaslight.github.io/gaslight-legal/privacy.html
**Terms of Service:** https://appgaslight.github.io/gaslight-legal/terms.html
**Impressum:** https://appgaslight.github.io/gaslight-legal/impressum.html

## Kontakt
appgaslight@gmail.com
