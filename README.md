# PixelWise - eine Web-App zur Erkennung handgeschriebener Ziffern
## Erweiterung: Rotierbare API-Schlüssel

Diese Erweiterung ergänzt die Authentifizierung um eine
Schlüssel-Rotation mit Übergangsfenster. Statt eines festen
`SECRET_API_KEY` enthält die `.env` eine Liste:

    API_KEYS=schluessel1,schluessel2

Die Prüfung erfolgt über `x_api_key not in valid_keys`. Beim
Rotieren bleiben alter und neuer Schlüssel kurz parallel gültig,
sodass Clients ohne Ausfall umstellen können; danach wird der
alte Schlüssel entfernt.

## Setup
1. `.env` aus `.env.example` erstellen und Werte eintragen
2. `pip install -r requirements.txt`
3. Start: `uvicorn app.main:app`

## Hinweis zu Secrets
Echte Schlüssel liegen nur in der lokalen `.env` (per `.gitignore`
ausgeschlossen). Das Repository enthält ausschließlich
`.env.example` mit Platzhaltern.
