# NEXUS KRISISHOP — GitHub + Apps Script + Google Sheets

## 1. Apps Script
1. Open the NEW Google Sheet.
2. Extensions → Apps Script.
3. Replace the project code with `Code.gs`.
4. If the script is bound to that Sheet, leave `SPREADSHEET_ID = ""`. Otherwise put the Sheet ID there.
5. Run `setupDatabase()` once and authorize.
6. Deploy → New deployment → Web app. Execute as **Me**. For a GitHub Pages frontend, choose the access option that permits your intended users.
7. Copy the `/exec` URL.

## 2. GitHub frontend
Open `app.js` and set:
```js
const API_URL = "YOUR_APPS_SCRIPT_WEB_APP_EXEC_URL";
const API_TOKEN = "";
const USE_DEMO = false;
```
If you set `API_TOKEN` in `Code.gs`, use the same value in `app.js`.

## 3. What is connected
- Products
- Companies / suppliers
- Customers
- Employees
- Stock
- Sales/POS with stock validation + FIFO backend
- Purchases + stock entry
- Customer payments
- Company payments
- Settings
- Dashboard refresh from Google Sheets

The frontend uses JSONP GET requests so it can run from GitHub Pages without depending on browser CORS headers from Apps Script.

## Important
Do not put a sensitive secret in a public GitHub repository. If the GitHub site is public and your API must be private, use a proper authenticated backend or keep the frontend restricted.
