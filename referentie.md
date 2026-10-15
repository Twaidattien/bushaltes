# Project Referentie: Live Buurtbus App Veendam

Dit bestand dient als geheugensteun voor de AI-assistent bij een volgende sessie. Hiermee kan de assistent direct de juiste context oppakken zonder dat alles opnieuw uitgelegd hoeft te worden.

## 📌 Project Status & Doel
* **Doel:** Een Single Page Webapp (HTML/CSS/JS) die op elk device draait en live bustijden + vertragingen toont voor specifieke buurt-haltes.
* **Hosting:** Gratis via GitHub Pages.
* **Architectuur:** De broncode zit volledig in `index.html`. De haltes worden dynamisch ingeladen vanuit een los configuratiebestand (`haltes.json`).
* **Data-bron:** OpenOV / OVapi (`https://ovapi.nl`).

## 🚌 Geconfigureerde Haltes (Veendam)
Op dit moment zijn de volgende drie haltes actief in `haltes.json`:
1. **J. Kazemierstraat** (TPC: `12639160`)
2. **Boven Westerdiep** (TPC: `12631810`)
3. **Julianalaan** (TPC: `12631830`)

## 🛠️ Huidige Uitdaging (Volgende Stap)
We hebben de JavaScript `fetch`-URL gecorrigeerd naar het volledige format met de `/tpc/` submap. De browser geeft op GitHub Pages echter nog een foutmelding (*"Kon live data niet ophalen"*). 
* **Oorzaak:** Een CORS-blokkade (beveiligingsrestrictie) vanuit de OVapi-server wanneer de data rechtstreeks in een HTTPS-browseromgeving wordt opgevraagd.
* **Laatst voorgestelde oplossing:** Het testen van een CORS-proxy (`cors-anywhere`) of het overstappen op een alternatieve methode (zoals een serverless functie of een API-oplossing die CORS-vriendelijk is) om de live data succesvol te tonen.

## 📋 Vragen voor de volgende sessie
Als we de draad weer oppakken, geef de AI-assistent dan de volgende updates:
1. **Resultaat CORS-test:** Heeft het activeren van de tijdelijke CORS-proxy demo (via ://herokuapp.com) de bustijden succesvol op het scherm gekregen?
2. **Duurzame oplossing:** Willen we vasthouden aan de proxy, of zullen we kijken naar een definitieve oplossing zonder handmatige activatieknop (zoals een gratis Fetch-script via Cloudflare Workers of Netlify)?
3. **Nieuwe Wensen:** Zijn er in de tussentijd haltes veranderd in `haltes.json`, of willen we de interface uitbreiden met een handmatige 'Ververs'-knop of automatische timer?
