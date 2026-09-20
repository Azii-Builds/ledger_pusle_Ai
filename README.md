# LedgerPulse

AI-powered document collection and reconciliation for small accounting firms

LedgerPulse takes the drudgery out of monthly closing by collecting documents from clients, extracting the relevant data using OCR, syncing bank statements, and reconciling every transaction with its invoice, letting CAs get back to the work people want them to do.
---

## The Problem

Small accounting firms waste countless hours a month on

- Manual data entry across Tally, Excel, bank statements andGST portals, which invites errors
- Following up with clients for missing bills, statements andinvoices
- Month-end closing checks across sales, purchases, expenses, payroll andbank balances
- Hidden errors in the form of duplicate bills, wrong entries,suspicious payments and missing invoices
- Audit paperwork, where the CA has to pull out proof for everyimportant entry
- Clients who cannot make sense of financial reports and just want to know"Why is my profit down?" or "Do I have enough money?"
- Juggling between many clients, each with their own deadlines,files and issues
LedgerPulse tackles the single most time-consuming task first - collecting documents from clients and reconciling them with the bank statements, and iteratively adds on more features.

## Features

### Core (MVP)
- Client document portal: Each client gets secure upload links and automatic reminders for missing documents (WhatsApp/email)
- OCR + data extraction: Pulls out vendor name, invoice number, date, GSTIN, taxes and totals from PDFs, scans and photos
- Bank sync: Real-time sync where available, or import PDF/CSV/Excel statements
- Auto-reconciliation: AI auto-matches bank transactions to invoices and ledger entries with confidence scores and a one-click review queue
- Duplicate and anomaly detection: Highlights duplicate bills, anomalous amounts, missing invoices and suspicious payments
- Multi-client dashboard: Deadlines, pending documents and reconciliation status per client

### Planned
- Tally (XML) and Excel import/export
- GST return cross-checks (GSTR-2B vs purchase register)
- Month-end closing checklist with suggested adjustments
- Audit pack generator with links to all supporting evidence
- "Ask your numbers" plain English assistant for CA clients
- Payroll and expense imports
- Role-based access and approvals, full audit trail

## How it works
```

Client uploads docs -> OCR + AI extraction -> Bank sync / statement import
|                          |
+----------> Auto-match and reconcile <-----------+
|
Review queue (exceptions only)
|
Tally/Excel export · Audit-ready pack
```

## Tech stack

| Layer | Choice |
|-------|--------|
| Frontend | React, TypeScript, Tailwind CSS |
| Backend | Python, FastAPI |
| Database | PostgreSQL |
| Storage | S3-compatible object storage |
| OCR / extraction | Document OCR with LLM-based field extraction |
| Matching engine | Rule-based matching + LLM for ambiguous cases |
| Bank data | Account Aggregator (India) / bank-feed provider + statement parsers |
| Queue | Redis and Celery |
| Auth | JWT + role-based access |
