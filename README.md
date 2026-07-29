# ka2eeu.net

Personal amateur radio site for callsign **KA2EEU**.

## Live site

Hosted on **Azure App Service** (Linux, **Node.js 24**):

https://ka2eeu-due0edfdaqf4fsac.centralus-01.azurewebsites.net

Custom domain planned: **www.ka2eeu.net**

Pushes to `main` deploy via GitHub Actions (`.github/workflows/main_ka2eeu.yml`).

## Local preview

```bash
npm install
npm start
```

Or open `index.html` directly in a browser.

## Deploy

Static site served by a small Node process (`npm start`) on Azure Linux Node 24. After domain cutover, add **www.ka2eeu.net** as a custom domain on the App Service and bind TLS.

## Customize

- Confirm the email in `index.html` (`scott@ka2eeu.net`)
- Add your Maidenhead grid square under Station interests
- Swap the hero SVG for a station/antenna photo if you prefer
