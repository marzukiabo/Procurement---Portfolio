# SCM Expeditor System

Expediting control for open purchase orders: which POs are late, who owns them, what to chase today, and a link the vendor can open to confirm ETA and shipping.

**Live demo:** [`expeditor/index.html`](index.html). All data is fictional and generated in the browser.

## The problem

Open PO data changes every day. Expeditors were re-pasting exports into spreadsheets, chasing vendors one by one on WhatsApp, and had no single view of aging, workload per buyer, or who had already been contacted.

## How it works

1. **Data in.** Open POs from the ERP land in one shared sheet automatically several times a day. POs that are received in the ERP drop out on the next refresh. (How the data is collected is private.)
2. **Rules.** Vendor ETA = PO date + ship days + 2 days. ETA actual is entered by the expeditor and overrides it. A PO needs follow-up from H-1 of its ETA if nothing is confirmed.
3. **Follow up.** Select POs, export an Excel for the vendor, or generate a combined WhatsApp message per vendor. Sending the message or copying the link moves the status to *Sudah di-WA* automatically.
4. **Vendor link.** A tokenised link (valid 2 days) shows only that vendor's POs and items. The vendor fills ETA and courier; status moves to *Waiting Shipment* / *In Transit*, and a past date means *delivered* and the PO leaves the list.
5. **Dashboard.** Load per site, overdue vs on-progress per buyer, arrivals per month, and average aging for All / Goods / Service.

## Features

- Dashboard: KPI cards, status per site, ETA due buckets, arrivals per month, per buyer / department / supplier stacked bars (overdue vs on progress, numbers inside), average aging, load share per site, priority counts
- Quick filters: overdue, backlog, breakdown, VHS, ETA needs confirmation, not followed up, due within 7 days; site, buyer and free-text search
- Follow Up PO table: expandable rows with items, PR description (codes such as BLC / DT / LV highlighted), ETA actual per PO and per item, colour-coded status dropdown, notes, per-PO history with who changed what
- Daily tracker: how many POs were followed up today and yesterday, and by whom
- Automatic status: message sent or link copied, ETA filled, courier chosen, ETA in the past
- Combined WhatsApp message per vendor, vendor link, multi-select Excel export (one file per vendor with an empty ETA column)
- Four-dot vendor progress marker and a colour per courier
- Vendor-side page for ETA per item and courier, print to PDF, usable on phone

## Stack

Google Sheets · Google Apps Script · HTML / CSS / vanilla JavaScript · Excel export

The production system, its spreadsheet, endpoints, keys and real data are private. This repository only contains the demo with fictional data.
