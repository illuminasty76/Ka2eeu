# ka2eeu.net

Personal amateur radio site for callsign **KA2EEU**.

## Live site

Hosted on **Azure App Service** (Linux, **Node.js 24**):

https://ka2eeu-due0edfdaqf4fsac.centralus-01.azurewebsites.net

Custom domain planned: **www.ka2eeu.net**

Pushes to `main` deploy via GitHub Actions (`.github/workflows/main_ka2eeu.yml`).

### Azure OIDC (federated identity)

This repo uses GitHub’s immutable OIDC subject. The Entra app registration federated credential for GitHub Actions must use this **exact** subject:

```text
repo:illuminasty76@25125527/Ka2eeu@1315673277:ref:refs/heads/main
```

Issuer: `https://token.actions.githubusercontent.com`  
Audience: `api://AzureADTokenExchange`

If login fails with `AADSTS700213`, update or recreate that federated credential to match the subject above (Portal → App registrations → your deploy app → Certificates & secrets → Federated credentials).

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
- Grid square is set to **EM20hc** (Spring / Old Town Spring area) — update if you change QTH
- Do not publish a street address on the site
- Swap the hero SVG for a station/antenna/repeater photo when you have one
