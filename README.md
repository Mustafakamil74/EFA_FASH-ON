# EFA FASHION ERP

A lightweight, single-file ERP for a fashion business (customers, shops, factories/suppliers,
invoices, payments, inventory and reports). The whole application is contained in **`index.html`** —
plain HTML, CSS and JavaScript with **no build step and no server**. All data is stored locally in the
browser's `localStorage`.

The interface is bilingual (Arabic / Türkçe) and right-to-left aware.

## Running

Open `index.html` in any modern browser, or serve the folder:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Modules

- **Dashboard** – low-stock alerts and upcoming/overdue cheques.
- **Customers** / **Shops** – contacts with a unique code, phone, address and note.
- **Factories** – suppliers (with a unique code).
- **Inventory** – product/SKU master and stock-on-hand per branch.
- **Invoices** – multi-line invoices per branch with computed line and invoice totals.
- **Accounts** – payments against invoices (cash / cheque / transfer), with remaining balance.
- **Reports** – customer balances & aging, sales summary and a cheque calendar.

## Data storage & backup

Data lives in `localStorage` under these keys: `customersData`, `shopsData`, `factoriesData`,
`productsData`, `efaInvoices`, `efaAccounts`.

Because the data is browser-local, **back it up regularly**:

- Each module has **Export** / **Import** buttons (JSON).
- The Dashboard has **Backup all** / **Restore all** to save or load every module in one file.

Clearing the browser's site data will erase everything, so keep backups.

## Development notes

- No dependencies, no toolchain — edit `index.html` directly.
- User-entered text is HTML-escaped before rendering to avoid injection.
- Records are addressed by a stable `id`, generated on save.
